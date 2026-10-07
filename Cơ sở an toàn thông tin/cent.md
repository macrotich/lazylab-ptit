
Dưới đây là tài liệu hướng dẫn hoàn chỉnh theo định dạng **Markdown**, được tối ưu bố cục rõ ràng để bạn copy trực tiếp tạo file `README.md` hoặc note đẩy lên GitHub:

```markdown
# Hướng Dẫn Thực Hành Lab: Exploring Unix Logs on CentOS (Labtainer)

Tài liệu chi tiết các bước thực hiện, giải thích câu lệnh và mẫu câu trả lời báo cáo cho bài thực hành **centos-log2**.

---

## I. Chuẩn Bị & Khởi Động Lab

1. Trên máy chủ Linux / VM Labtainer, mở terminal và chuyển vào thư mục bài lab:
   ```bash
   cd labtainer/labtainer-student
   labtainer centos-log2

```

2. Đăng nhập vào tài khoản user trên máy CentOS:
* **Username:** `joe`
* **Password:** `password4joe`



---

## II. Các Bước Thực Hiện Chi Tiết

### Phần III: Khảo sát hệ thống Log (Explore)

#### 1 & 2. Đăng nhập thử quyền root (`su`)

* Gõ lệnh `su` và nhập sai mật khẩu một lần.
* Gõ lại `su` và nhập mật khẩu root đúng: `badpassword`.
* Dấu nhắc lệnh chuyển thành `#` biểu thị quyền root.

#### 3. Khảo sát thư mục `/var/log`

```bash
cd /var/log
ls -l
ls -l messages

```

* **Báo cáo (Item #1):** Quyền hạn của user thông thường đối với file `/var/log/messages`:
* *Trả lời:* File có quyền `-rw-------` (hoặc tương tự theo máy), thuộc sở hữu của `root:root`. Người dùng thông thường (*others*) không có bất kỳ quyền đọc hay ghi nào (`---` / no permissions).



#### 4. Kiểm tra lịch sử đăng nhập sai

```bash
less /var/log/secure
# Nhấn phím 'G' để xuống cuối file, tìm các sự kiện liên quan đến joe

```

* **Báo cáo (Item #2):** Cụm từ thông báo đăng nhập thất bại:
* *Trả lời:* `FAILED LOGIN 1 FROM ... FOR joe, Authentication failure` hoặc `Failed password for joe`.


* **Báo cáo (Item #3):** Trả lời câu hỏi tiếp theo trong báo cáo về địa chỉ IP hoặc cổng tương ứng được ghi lại trong log.

#### 5. Kiểm tra thông tin lệnh `su`

* Cuộn xuống cuối file `/var/log/secure` để xem dòng log của phiên `su`:
```bash
grep -i "su:" /var/log/secure | tail -n 10

```


* **Báo cáo (Item #5):** Thông tin được ghi lại khi thực hiện lệnh `su`:
* *Trả lời:* Ghi nhận sự kiện xác thực thất bại `pam_unix(su:auth): authentication failure; logname=joe uid=1000 euid=0 tty=pts/... ruser=joe rhost= user=root` và sự kiện thành công `pam_unix(su:session): session opened for user root by joe(uid=1000)`.



#### 6. Tra cứu lệnh `last` và file `wtmp`

```bash
man last
# Nhấn 'q' để thoát trang man

```

* **Báo cáo (Item #6):** Chức năng của tùy chọn `-t`:
* *Trả lời:* Tùy chọn `-t YYYYMMDDHHMMSS` cho phép hiển thị trạng thái đăng nhập của hệ thống tính đến một mốc thời gian xác định trong quá khứ. Điều này giúp quản trị viên tra cứu ai đang đăng nhập vào hệ thống tại một thời điểm cụ thể (thông qua trạng thái `still logged in`).



---

### Phần IV: Cấu Hình Tính Năng MARK Cho rsyslog

1. Mở file cấu hình rsyslog:
```bash
nano /etc/rsyslog.conf

```


2. Tìm đến mục `#### MODULES ####`:
* Bỏ dấu `#` trước dòng:
```text
$ModLoad immark

```


* Thêm dòng thiết lập chu kỳ (60 giây) ngay bên dưới:
```text
$MarkMessagePeriod 60

```


* Nhấn `Ctrl + O` để lưu, `Ctrl + X` để thoát.


3. Khởi động lại dịch vụ `rsyslog`:
```bash
systemctl restart rsyslog

```


4. Theo dõi log thời gian thực:
```bash
tail -f /var/log/messages

```


* Chờ khoảng 1 phút sẽ thấy dòng `-- MARK --` xuất hiện. Nhấn `Ctrl + C` để thoát.



---

### Phần V: Tùy Biến Luật rsyslog & Tiện Ích logger

#### 1 & 2. Gửi thử một log với độ ưu tiên `info`

```bash
logger -p info "Hello World"

```

*(Nếu không chỉ định facility, mặc định sẽ là `user`)*

#### 3 & 4. Xác định luật xử lý

* Mở `/etc/rsyslog.conf`, xem mục `#### RULES ####`.
* **Báo cáo (Item #7):** Dòng luật đã xử lý log `info`:
* *Trả lời:* `*.info;mail.none;authpriv.none;cron.none                /var/log/messages`



#### 5. Xác minh log đã lưu

```bash
grep "Hello World" /var/log/messages

```

#### 6, 7 & 8. Thêm luật mới chỉ lưu log `debug` vào `/var/log/mydebug`

* Mở lại `/etc/rsyslog.conf`:
```bash
nano /etc/rsyslog.conf

```


* Thêm vào phần `#### RULES ####` dòng sau:
```text
*.=debug                                                /var/log/mydebug

```


*(Dấu `=` đảm bảo chỉ ghi nhận chính xác mức `debug`, không ghi nhận các mức cao hơn)*
* **Báo cáo (Item #8):** Ghi lại luật trên: `*.=debug    /var/log/mydebug`.
* Lưu file và khởi động lại dịch vụ:
```bash
systemctl restart rsyslog

```



#### 9. Kiểm tra luật mới

```bash
logger -p user.debug "Test debug message"
cat /var/log/mydebug

```

* **Báo cáo (Item #9):** Mô tả cách kiểm tra:
* *Trả lời:* Dùng lệnh `logger -p user.debug "Test debug message"` để sinh log mức debug, sau đó kiểm tra tệp `/var/log/mydebug` bằng lệnh `cat` để xác nhận thông điệp đã được ghi thành công, đồng thời kiểm tra `/var/log/messages` để đảm bảo log không bị trùng hoặc xử lý đúng theo cấu hình.



#### 10. Phân quyền thực thi cho lệnh `logger`

* Kiểm tra quyền hiện tại:
```bash
ls -l /bin/logger

```


* Thu hồi quyền thực thi của người dùng thông thường (chỉ cho phép user root và group root thực thi):
```bash
chmod 750 /bin/logger
# hoặc: chmod o-rwx /bin/logger

```


* **Báo cáo (Item #10):** Ghi lại câu lệnh đã sử dụng: `chmod 750 /bin/logger`.

---

### Phần VI: Centralized Logging (Thu Thập Log Tập Trung)

#### 1, 2 & 3. Cấu hình máy Logger (máy nhận log)

* Mở `/etc/rsyslog.conf` trên máy logger:
```bash
nano /etc/rsyslog.conf

```


* Tìm và bỏ dấu comment `#` ở các dòng tiếp nhận qua UDP và TCP trên cổng 514:
```text
$ModLoad imudp
$UDPServerRun 514
$ModLoad imtcp
$InputTCPServerRun 514

```


* Khởi động lại `rsyslog`:
```bash
systemctl restart rsyslog

```


* Kiểm tra địa chỉ IP của máy logger:
```bash
ifconfig

```


*(Thông thường là `172.25.0.2`)*

#### 4 & 5. Mở máy Workstation

* Tại terminal của máy host Linux, mở terminal kết nối đến máy workstation:
```bash
moreterm.py centos-log2 workstation

```



#### 6. Lắng nghe log trên máy Logger

* Quay lại terminal máy **logger**, chạy lệnh theo dõi:
```bash
tail -f /var/log/messages

```



#### 7, 8, 9 & 10. Cấu hình chuyển tiếp trên máy Workstation

* Trên terminal máy **workstation**, nâng quyền root:
```bash
sudo su

```


* Mở file `/etc/rsyslog.conf`:
```bash
nano /etc/rsyslog.conf

```


* Kéo xuống cuối phần `#### RULES ####`, thêm dòng chuyển tiếp toàn bộ log đến IP máy logger (dùng UDP qua cú pháp `@`):
```text
*.* @172.25.0.2

```


* Khởi động lại dịch vụ rsyslog trên workstation:
```bash
systemctl restart rsyslog

```



#### 11. Kiểm tra gửi nhận log từ Workstation sang Logger

* Trên máy **workstation**, phát thử một thông điệp:
```bash
logger "Log test tu workstation"

```


* Quan sát terminal máy **logger** đang chạy `tail -f /var/log/messages`, kiểm tra xem có dòng log gửi từ hostname của máy workstation hay không.

---

## III. Kết Thúc & Đóng Gói Bài Nộp

1. Hoàn thiện các câu hỏi khảo sát cuối bài (Item #11 đến #16) trong file báo cáo (`lab report template`).
2. Đảm bảo file báo cáo đã được lưu vào đúng đường dẫn hiển thị lúc khởi động lab.
3. Trở về terminal chính trên host Linux và dừng bài thực hành:
```bash
stoplab

```


4. Hệ thống sẽ tạo một file `.zip` kết quả lưu tại đường dẫn được hiển thị trên terminal. Lấy file này nộp theo yêu cầu của giảng viên.

```

```

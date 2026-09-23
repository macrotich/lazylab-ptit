# 🛡️ Lab: Giới thiệu về module xác thực PAM (aaa-lin-pam-bsic)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal nhập :
```
ls -la /etc/pam.d/
```
```
cat /etc/pam.d/common-auth
```
```
sudo tail /var/log/auth.log
```

#### Bước 2:
Trên terminal nhập lệnh:
```
sudo passwd user1
```
Nhập mật khẩu(2 lần):
```
test
```
```
sudo nano /etc/pam.d/common-auth
```
Xóa dấu **`#`** dòng **`auth    [success=1 default=ignore]    pam_unix.so nullok_secure`**
```
su user1
```
Nhập mật khẩu:
```
test
```
```
exit
```
```
sudo tail /var/log/auth.log
```
#### Bước 3:
Trên terminal nhập lệnh:
```
sudo nano /etc/pam.d/common-auth
```
Điền dòng sau vô trên dòng có **`pam_unix.so`**:
```
auth required pam_tally2.so deny=3 unlock_time=600
```
```
sudo nano /etc/pam.d/common-account
```

## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

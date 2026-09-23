# 🛡️ Lab: Bẻ khóa mật khẩu (atk-pass-crack)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal nhập :
```
chage -l student
```
#### Bước 2:
Trên terminal nhập :
```
./crackSHA.py htpasswd-sha1 tinylist.txt
```
#### Bước 3:
Trên terminal nhập :
```
./crackMD5.py htpasswd-md5 biglist.txt
```
```
./crack512.py htpasswd-sha512 biglist.txt
```
```
./crackPre.py htpasswd-sha1 calc
```
#### Bước 4:
Trên terminal nhập :
```
htpasswd -sc htpasswd-me alice
```
Nhập mật khẩu(2 lần):
```
ubuntu
```

## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

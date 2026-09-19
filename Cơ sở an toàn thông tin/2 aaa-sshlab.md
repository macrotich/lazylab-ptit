# 🛡️ Lab: SSH Lab – Xác thực bằng cặp khóa SSH và quản lý truy cập an toàn(aaa-sshlab)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal **`client`** nhập :
```
ssh-keygen -t rsa
```
(Nhấn Enter 3 lần)
```
ssh-copy-id -i ~/.ssh/id_rsa.pub 172.20.0.3
```
Khi được hỏi thì nhập:
```
yes
```
Mật khẩu nhập:
```
ubuntu 
```
#### Bước 2:
Trên terminal **`client`**, nhập lệnh:
```
ssh ubuntu@172.20.0.3
```
   
```
cat filetoview.txt
```


## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

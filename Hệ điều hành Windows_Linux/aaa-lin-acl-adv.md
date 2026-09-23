# 🛡️ Lab: Quản lý quyền truy cập và quyền kế thừa file với danh sách quản lý quyền truy cập (aaa-lin-acl-adv)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal nhập :
```
sudo setfacl -m u:user1:rwx project
```
```
sudo setfacl -m u:user2:r project
```
```
sudo setfacl -m u:user3:rx project
```
```
sudo getfacl project
```
#### Bước 2:
Trên terminal nhập :
```
sudo setfacl -dR -m u:user1:rwx project
```
```
sudo setfacl -dR -m u:user3:rx project
```
```
sudo setfacl -dR -m u:user2:r project
```
```
sudo getfacl project
```
#### Bước 3:
Trên terminal nhập :
```
sudo getfacl project/subdir1 project/file1
```
#### Bước 4:
Trên terminal nhập :
```
sudo setfacl -dR -m u:user2:rwx project
```
```
sudo getfacl project
```
```
sudo getfacl project/subdir2 project/file2
```
## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

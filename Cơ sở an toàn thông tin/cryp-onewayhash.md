# 🛡️ Lab: Hàm băm một chiều và MAC (cryp-onewayhash)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
```
openssl dgst -md5 filetodigest.txt
```
```
openssl dgst -sha1 filetodigest.txt
```
```
openssl dgst -sha256 filetodigest.txt
```

#### Bước 2:
```
openssl dgst -md5 -hmac "testing" filetodigest.txt
```
```
openssl dgst -sha1 -hmac "testing" filetodigest.txt
```
```
openssl dgst -sha256 -hmac "testing" filetodigest.txt
```
#### Bước 3:
```
echo "testingagain" > edit-this-file.txt
```
```
cat edit-this-file.txt
```
```
openssl dgst -md5 edit-this-file.txt
```
```
hexedit edit-this-file.txt
```
Sửa một ký tự bất kỳ xong nhấn cltr+x
```
openssl dgst -sha256 edit-this-file.txt
```


## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

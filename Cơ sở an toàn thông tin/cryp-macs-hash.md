# 🛡️ Lab: Tìm hiểu về hàm băm và mã xác thực thông điệp MACs (cryp-macs-hash)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal nhập :
```
nano myfile.txt
```
Nhập nội dung:
```
testing
```
(Nhấn Ctrl+O rồi Ctrl+X)
```
shasum -a 1 myfile.txt
```
```
shasum -a 224 myfile.txt
```
```
shasum -a 256 myfile.txt
```
```
shasum -a 384 myfile.txt
```
```
shasum -a 512 myfile.txt
```
```
shasum -a 512224 myfile.txt
```
```
shasum -a 512256 myfile.txt
```
#### Bước 2:
Trên terminal nhập :
```
lynx verydodgy.com
```
Bấm D rồi nhấn 2 lần enter rồi bấm q 
```
lynx verydodgy.com
```
Bấm mũi tên xuống rồi bấm D rồi nhấn 2 lần enter rồi bấm q 
```
shasum -a 256 floppy57.fs
```
```
shasum -a 256 SHA256.sdx
```
#### Bước 3:
Trên terminal nhập :
```
echo "Bob owes me 200 dollars" > iou.txt
```
```
shasum -a 256 iou.txt
```
#### Bước 4:
Trên terminal nhập :
```
shasum -a 256 declare.txt
```
```
./collide1.sh declare.txt 1
```
```
./collide1.sh declare.txt 2
```
```
./collide1.sh declare.txt 3
```
```
./collide2.py
```
#### Bước 5: 
Trên terminal nhập :
```
openssl dgst -sha1 -hmac mykey foo.txt
```
```
openssl dgst -sha1 -hmac 0 declare.txt
```
```
openssl dgst -sha1 -hmac 1 declare.txt
```
```
openssl dgst -sha1 -hmac 2 declare.txt
```
```
openssl dgst -sha1 -hmac 3 declare.txt
```
```
openssl dgst -sha1 -hmac 4 declare.txt
```
```
openssl dgst -sha1 -hmac 5 declare.txt
```
```
openssl dgst -sha1 -hmac 6 declare.txt
```
```
openssl dgst -sha1 -hmac 7 declare.txt
```
```
openssl dgst -sha1 -hmac 8 declare.txt
```
```
openssl dgst -sha1 -hmac 9 declare.txt
```
## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

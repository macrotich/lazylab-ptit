# 🛡️ Lab: Khám phá các chế độ mã hóa khóa đối xứng (symkeylab)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal nhập :
```
echo "qua luoi de lam" > plain.txt
```
```
openssl aes-128-cbc -e -in plain.txt -out cipher.txt -K 0123456789ABCDEF0123456789ABCDEF -iv 00000000000000000000000000000000
```
```
hexdump -C cipher.txt
```
```
diff -a plain.txt plainmod.txt
```
#### Bước 2:
Trên terminal  nhập lệnh:
```
openssl aes-128-ecb -e -in plain.txt -out cipher_ecb.bin -K 00112233445566778899aabbccddeeff
```
```
openssl aes-128-cbc -e -in plain.txt -out cipher_cbc.bin -K 00112233445566778899aabbccddeeff -iv 0102030405060708090a0b0c0d0e0f10
```
```
openssl aes-128-ofb -e -in plain.txt -out cipher_ofb.bin -K 00112233445566778899aabbccddeeff -iv 0102030405060708090a0b0c0d0e0f10
```
```
dd if=cipher_cbc.bin of=cipher_corrupt.bin bs=1 count=16
```
#### Bước 3:
Trên terminal nhập lệnh:
```
hexedit cipher_cbc.bin
```
(Nhấn Ctrl+X)
```
ghex ENCRYPTEDFILE
```



## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

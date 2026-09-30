# 🛡️ Lab: Khám phá các chế độ mã hóa khóa đối xứng (cryp-symkeylab)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal nhập :
```
echo "doan van ban" > plain.txt
```
```
openssl CIPHER -e -in plain.txt -out cipher.txt -K KEY -iv IV
```
```
hexdump -C cipher.txt
```
```
openssl CIPHER -d -in cipher.txt -out plainmod.txt -K KEY -iv IV
```
```
diff -a plain.txt plainmod.txt
```
#### Bước 2:
Trên terminal  nhập lệnh:
```
./start_firefox &
```
```
dd if=nps-logo.bmp of=nps-logo_mod.bmp bs=1 count=54 conv=notrunc
```
```
openssl -aes-128-ecb -e -in nps-logo.bmp -out nps-logo_ecb.bmp -K 00112233445566778899aabbccddeeff
```
```
openssl -aes-128-cbc -e -in nps-logo.bmp -out nps-logo_cbc.bmp -K 00112233445566778899aabbccddeeff -iv 0102030405060708090a0b0c0d0e0f10
```
```
openssl -aes-128-cfb -e -in nps-logo.bmp -out nps-logo_cfb.bmp -K 00112233445566778899aabbccddeeff -iv 0102030405060708090a0b0c0d0e0f10
```
```
openssl -aes-128-ofb -e -in nps-logo.bmp -out nps-logo_ofb.bmp -K 00112233445566778899aabbccddeeff -iv 0102030405060708090a0b0c0d0e0f10
```
#### Bước 3:
Trên terminal **`ws3`** nhập lệnh:
```
sudo nano /etc/resolv.conf
```
Điền dòng sau vô:
```
search example.com
nameserver 192.168.0.3
```


## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

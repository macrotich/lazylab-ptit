# 🛡️ Lab: Khám phá các chế độ mã hóa khóa đối xứng (cryp-symkeylab)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal **`dns`** nhập :
```
sudo nano /var/named/example.com.zone
```
Chèn thêm dòng sau vào cuối:
```
ws3     IN      A       192.168.0.3
```
(Nhấn Ctrl+O rồi Ctrl+X)
```
sudo nano /var/named/192.168.0.0
```
Chèn thêm dòng sau vào cuối:
```
13      IN      PTR     ws3
```
(Nhấn Ctrl+O rồi Ctrl+X)
```
sudo systemctl restart bind9
```
#### Bước 2:
Trên terminal **`ws1`**, nhập lệnh:
```
ping -c 3 ws3
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

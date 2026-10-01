# 🛡️ Lab: Hạn chế truy cập SSH bằng công cụ denyhost (net-denyhost)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal **`client`** nhập :
```
ssh hank@172.20.0.3
```
```
yes
```
```
hank21
```
```
exit
```
#### Bước 2:
Trên terminal **`client`** nhập :
```
 ./bot.py hank
```
(Nhấn Ctrl+C)

#### Bước 3:
Trên terminal **`server`** nhập :
```
echo "ALL: 172.20.0.2" | sudo tee -a /etc/hosts.allow
```
```
sudo iptables -D INPUT -s 172.20.0.2 -j DROP
```
Trên terminal **`client`** nhập :
```
ssh hank@172.20.0.3
```
```
hank21
```
```
exit
```
#### Bước 4:
Trên terminal **`client`** nhập :
```
sudo ifconfig eth0 172.20.0.9
```
```
 ./bot.py tony
```
(Nhấn Ctrl+C)
## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

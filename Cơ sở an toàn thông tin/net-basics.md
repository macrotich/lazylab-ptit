# 🛡️ Lab: Các giao thức mạng cơ bản (net-basics)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal **`box1`** nhập :
```
sudo tcpdump -vv -n -i eth0
```
Trên terminal **`box2`**, nhập lệnh:
```
ssh 172.0.0.2
```
```
yes
```
#### Bước 2:
Trên terminal **`box1`** nhập :
(Nhấn Ctlr+C rồi enter)
```
sudo tcpdump -vv -n -e -i eth0
```
Trên terminal **`box2`**, nhập lệnh:
(Nhấn Ctlr+C)
```
arp -a
```



## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

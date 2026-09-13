# 🛡️ Lab: Sử dụng Nmap nâng cao (atk-nmap-ssh)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal **`mycomputer`** nhập :
```
   nmap -p 2000-3000 172.25.0.2
```
#### Bước 2:
Trên terminal **`router`**, nhập lệnh:
```
    sudo tcpdump -i any -X tcp
```
    (Nhấn Ctrl + C)
```
    sudo tshark -T fields -e telnet.data -i eth1
```
    (Nhấn Ctrl + C)

#### Bước 3:
Trên terminal **`mycomputer`** nhập lệnh:
```
    ssh -p 2907 ubuntu@172.25.0.2
```
Khi được hỏi thì nhập:
    yes

Nhập mật khẩu:
```
    8064f9ecdefc9b678771fa5fee4cb44d
```

Nhập:
```
    cat secretfile.txt
```


## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — All rights reserved.**

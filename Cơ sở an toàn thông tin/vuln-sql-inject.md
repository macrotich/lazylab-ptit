# 🛡️ Lab: SQL Inject Lab – Khai thác lỗ hổng SQL injection (vuln-sql-inject)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal **`server`** nhập :
```
mysql -u root -pseedubuntu
```

```
use Users;
```

```
show tables;
```

```
SELECT * FROM credential;
```


#### Bước 2:
Trên terminal **`client`**, nhập lệnh(2 lần):
```
curl 'http://www.SEEDLabSQLInjection.com/unsafe_credential.php?EID=10000&Password=111'
```

## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
© lazylab-ptit — Released under the MIT License

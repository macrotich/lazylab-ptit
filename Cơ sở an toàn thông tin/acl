# 🛡️ Lab: Danh sách điều khiển truy cập trên Linux (acl)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal **`1`** nhập :
```
bob
```

```
password4bob
```
Trên terminal **`2`** nhập :
```
alice
```

```
password4alice
```
Trên terminal **`3`** nhập :
```
harry
```

```
password4harry
```

#### Bước 2:
Trên terminal **`bob`**, nhập lệnh:
```
setfacl -m user:alice:r /shared_data/bob/bobstuff.txt
```
Trên terminal **`alice`**, nhập lệnh:
```
cat /shared_data/bob/bobstuff.txt
```  

#### Bước 3:
Trên terminal **`alice`**, nhập lệnh:
```
setfacl -d -m user:bob:r /shared_data/alice
```

```
setfacl -d -m o::--- /shared_data/alice
```
```
touch /shared_data/alice/test1.txt
```
Trên terminal **`bob`**, nhập lệnh:
```
cat /shared_data/alice/test1.txt
``` 

#### Bước 4:
Trên terminal **`bob`**, nhập lệnh:
```
nano /shared_data/bob/fun
```
Chèn thêm dòng sau vào cuối:
```
cp /shared_data/accounting.txt /shared_data/alice/stolen.txt
setfacl -m u:bob:r /shared_data/alice/stolen.txt
```
(Nhấn Ctrl+O rồi Ctrl+X)

Trên terminal **`alice`**, nhập lệnh:
```
/shared_data/bob/fun
``` 

## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

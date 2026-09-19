# 🛡️ Lab: Giới thiệu về quản lý người dùng, nhóm và quyền đối với tệp trên hệ thống Unix (aaa-users)

## Các bước thực hiện & Chuỗi lệnh (Solution)

#### Bước 1: 
Trên terminal **`1`** nhập :
```
admin
```
Nhập mật khẩu:
```
password123
```

#### Bước 2:
Trên terminal **`1`**, nhập lệnh:
```
sudo useradd -m bob
```
Nhập mật khẩu:
```
password123
```   
```
sudo passwd bob
```
Nhập mật khẩu(nhập 2 lần):
```
test
```


#### Bước 3:
Trên terminal **`1`**, nhập lệnh:
```
sudo useradd -m mary
```
   
```
sudo passwd mary
```
Nhập mật khẩu(nhập 2 lần):
```
test
```

```
sudo usermod -a -G bakers mary
```
Trên terminal **`2`**, nhập lệnh:
```
mary
```
Nhập mật khẩu:
```
test
```

```
cat /shared_stuff/tarts.txt
```

```
eggcheck /shared_stuff/tarts.txt
```

```
exit
```

#### Bước 4:
Trên terminal **`2`**, nhập lệnh:
```
bob
```
Nhập mật khẩu:
```
test
```

```
cat /shared_stuff/tarts.txt
```

```
cat /tmp/tmpfile.txt
```

```
exit
```

#### Bước 5:
Trên terminal **`1`**, nhập lệnh:
```
sudo useradd -m lisa
```
   
```
sudo passwd lisa
```
Nhập mật khẩu:
```
test
```
```
sudo usermod -a -G admin lisa
```

Trên terminal **`2`**, nhập lệnh:
```
lisa
```
Nhập mật khẩu:
```
test
```

```
sudo sudo userdel bob
```

## 📌 Bản quyền & Ghi công (Credits)

* **Tác quyền:** Tài liệu và nội dung giải pháp này thuộc dự án **lazylab-ptit** (Biên soạn bởi **Mạc Rô Tích**).
* **Điều khoản chia sẻ:** Cho phép tự do tham khảo và chia sẻ trong cộng đồng sinh viên với mục đích học tập phi thương mại.
* **Quy định trích dẫn:** Mọi hành vi sao chép một phần hoặc toàn bộ tài liệu vui lòng **giữ nguyên nguồn trích dẫn** và liên kết gốc của dự án `lazylab-ptit`. Nghiêm cấm hành vi tự nhận tác quyền hoặc sử dụng vào mục đích thương mại, mua bán tài liệu dưới mọi hình thức.

> *"Lười một cách thông minh, chia sẻ để cùng tiến bộ."*  
> **© lazylab-ptit — Released under the MIT License**

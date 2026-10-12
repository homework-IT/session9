# Bài 2: Khởi chạy Web Server Nginx với Port Mapping

## 1. Khởi chạy container Nginx

**Lệnh thực hiện:**

```bash
docker run -d -p 8080:80 --name my-web nginx:alpine
```

**Giải thích:**
- `-d`: Chạy container ở chế độ nền.
- `-p 8080:80`: Ánh xạ cổng 8080 của máy tính vào cổng 80 của container.
- `--name my-web`: Đặt tên container là `my-web`.
- `nginx:alpine`: Sử dụng image Nginx phiên bản Alpine nhẹ.

**Kết quả:** Docker trả về ID của container nếu khởi chạy thành công.

## 2. Kiểm tra container đang chạy

**Lệnh thực hiện:**

```bash
docker ps
```

**Kết quả mong đợi:** Container `my-web` có trạng thái `Up` và ánh xạ cổng `0.0.0.0:8080->80/tcp` (hoặc tương đương).

## 3. Kiểm tra Web Server bằng curl

**Lệnh thực hiện:**

```bash
curl http://localhost:8080
```

**Kết quả mong đợi:** Lệnh trả về mã HTML của trang mặc định Nginx, có nội dung:

```html
<title>Welcome to nginx!</title>
<h1>Welcome to nginx!</h1>
```

Điều này xác nhận Web Server Nginx hoạt động và cổng 8080 đã được ánh xạ thành công.

## 4. Dừng và xóa container

**Lệnh thực hiện:**

```bash
docker stop my-web
docker rm my-web
```

Hoặc thực hiện cả hai lệnh cùng lúc:

```bash
docker stop my-web && docker rm my-web
```

**Kết quả mong đợi:** Container `my-web` được dừng và xóa khỏi hệ thống.

Kiểm tra lại:

```bash
docker ps -a
```

Container `my-web` không còn xuất hiện trong danh sách.

## 5. Kết luận

Đã thực hành khởi chạy Nginx bằng Docker ở chế độ nền, ánh xạ cổng 8080 của máy tính tới cổng 80 trong container, kiểm tra phản hồi HTTP bằng `curl` và dọn dẹp container sau khi hoàn thành.

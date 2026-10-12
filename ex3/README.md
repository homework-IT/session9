# Bài 3: Đóng gói trang Web HTML tĩnh bằng Docker

## 1. Tạo trang HTML

Tạo file `index.html` với nội dung:

```html
<h1>Hello Docker Session 09!</h1>
```

## 2. Viết Dockerfile

```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
```

- `FROM nginx:alpine`: Sử dụng image Nginx Alpine làm image cơ sở.
- `COPY`: Sao chép file HTML vào thư mục mặc định của Nginx để phục vụ trang web.

## 3. Build Docker Image

**Lệnh thực hiện:**

```bash
docker build -t my-html-app:v1 .
```

Lệnh này tạo image có tên `my-html-app` và tag `v1` từ Dockerfile trong thư mục hiện tại.

## 4. Khởi chạy container

**Lệnh thực hiện:**

```bash
docker run -d -p 8081:80 --name html-app my-html-app:v1
```

Container chạy ở chế độ nền và ánh xạ cổng 8081 trên máy tính tới cổng 80 của Nginx.

## 5. Kiểm tra kết quả

**Lệnh thực hiện:**

```bash
curl http://localhost:8081
```

**Kết quả mong đợi:**

```html
<h1>Hello Docker Session 09!</h1>
```

## 6. Kiểm tra image và container

```bash
docker images
docker ps
```

- `docker images`: Kiểm tra image `my-html-app:v1`.
- `docker ps`: Kiểm tra container `html-app` đang chạy.

## 7. Dọn dẹp sau khi thực hành

```bash
docker stop html-app
docker rm html-app
```

## 8. Kết luận

Đã tạo trang HTML tĩnh, viết Dockerfile sử dụng Nginx Alpine, build image `my-html-app:v1` và chạy ứng dụng trên cổng 8081. Kết quả được xác nhận bằng lệnh `curl` khi trả về nội dung HTML đã tạo.

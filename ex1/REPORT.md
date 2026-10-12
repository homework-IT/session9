# Bài 1: Kiểm tra cài đặt Docker Engine và chạy Container Hello-World

## 1. Kiểm tra phiên bản Docker

**Lệnh thực hiện:**
```bash
docker version
```

**Kết quả:**

```text
Client:
 Version:           [Phiên bản Docker của máy]
 API version:       [Phiên bản API]
 OS/Arch:           windows/amd64

Server:
 [Thông tin Docker Engine thực tế]
```

## 2. Kiểm tra thông tin Docker Engine

**Lệnh thực hiện:**
```bash
docker info
```

**Kết quả:**

```text
Client:
 Context:    desktop-linux

Server:
 Containers: [Số lượng container]
 Images:     [Số lượng image]
 Server Version: [Phiên bản Docker Engine]
 Operating System: [Hệ điều hành]
 Architecture: x86_64
```

## 3. Chạy container Hello World

**Lệnh thực hiện:**
```bash
docker run hello-world
```

**Kết quả mong đợi:**

```text
Hello from Docker!
This message shows that your installation appears to be working correctly.
```

Docker sẽ tải image `hello-world` nếu máy chưa có, sau đó tạo và chạy container để hiển thị thông báo xác nhận.

## 4. Kết luận

Đã thực hành ba lệnh cơ bản `docker version`, `docker info` và `docker run hello-world` để kiểm tra Docker CLI, Docker Engine và khả năng chạy container.

Khi lệnh `docker run hello-world` hiển thị thông báo thành công, có thể xác nhận Docker hoạt động bình thường.

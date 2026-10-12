# Bài 4: Lưu trữ dữ liệu đơn giản với Docker Volume

## 1. Tạo Docker Volume

**Lệnh thực hiện:**

```bash
docker volume create easy-volume
```

Lệnh này tạo một Named Volume có tên `easy-volume` để lưu trữ dữ liệu bền vững.

## 2. Ghi dữ liệu vào Volume

**Lệnh thực hiện:**

```bash
docker run --rm -v easy-volume:/data alpine sh -c "echo 'Luu tru du lieu Docker' > /data/test.txt"
```

**Giải thích:**
- `--rm`: Tự động xóa container sau khi chạy xong.
- `-v easy-volume:/data`: Gắn Volume `easy-volume` vào thư mục `/data` trong container.
- `alpine`: Sử dụng image Alpine Linux nhẹ.
- `echo`: Ghi nội dung vào file `/data/test.txt`.

## 3. Đọc dữ liệu từ container thứ hai

**Lệnh thực hiện:**

```bash
docker run --rm -v easy-volume:/data alpine cat /data/test.txt
```

**Kết quả mong đợi:**

```text
Luu tru du lieu Docker
```

Kết quả cho thấy dữ liệu vẫn tồn tại dù container đầu tiên đã kết thúc và bị xóa.

## 4. Kiểm tra danh sách Volume

**Lệnh thực hiện:**

```bash
docker volume ls
```

Kiểm tra xem Volume `easy-volume` có trong danh sách hay không.

## 5. Kết luận

Đã tạo Named Volume `easy-volume`, ghi dữ liệu vào Volume bằng một container Alpine và đọc lại dữ liệu bằng container Alpine thứ hai.

Kết quả xác nhận Docker Volume giúp lưu trữ dữ liệu độc lập với vòng đời của container, vì vậy dữ liệu vẫn tồn tại sau khi container dừng hoặc bị xóa.

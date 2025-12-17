Docker là công cụ phổ biến nhất để tạo và quản lý Container.

**Các thành phần chính của Docker:**

1. **Docker Engine**: "Động cơ" chạy ngầm, chịu trách nhiệm tạo và quản lý các container.
2. **Docker Client (CLI)**: Công cụ dòng lệnh (```docker run```    , ```docker build```   ...) để bạn ra lệnh cho Docker Engine.
3. **Docker Desktop**: Ứng dụng có giao diện (GUI) cho Windows/Mac, giúp cài đặt và quản lý Docker dễ dàng hơn.
4. **Docker Hub**: "Chợ ứng dụng" (Registry) nơi lưu trữ hàng triệu Docker Image (Ubuntu, Python, Nodejs, MySQL...). Bạn có thể tải về dùng miễn phí.
5. **Dockerfile**: Tờ giấy hướng dẫn (công thức) để Docker biết cách "xây" (build) ra một Image.

**Quy trình cơ bản:** 
```Dockerfile``` --(build)--> ```Docker Image``` --(run)--> ```Docker Container```
**Câu hỏi:** Để tạo ra một Docker Image cho ứng dụng của bạn, bạn cần viết một file cấu hình chứa các bước cài đặt (ví dụ: cài Python, copy code vào, cài thư viện...). File đó tên là gì? 
A. ```docker-compose.yml```
B. ```Dockerfile``` (không có đuôi mở rộng) 
C. ```package.json```
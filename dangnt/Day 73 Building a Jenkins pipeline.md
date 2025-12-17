Xây dựng 1 pipeline thực tế để build Docker image, Đẩy lên docker hub
**1. Kaniko:**
-  Để build Docker Image bên trong Kubernetes (Nơi Jenkisn đang chạy), chúng ta không nên dùng "Docker in Docker" (rất rủi ro về bảo mật)
- Giải pháp thay thế là **Kaniko**: Công cụ của Google giúp build container image từ Dockerfile mà không cần Docker daemon.
**2. Quy trình Pipeline**:
- **Get the project**: Lấy code từ Github.
- **Test**: Chạy test (Ví dụ: In ra ```pwd``` hoặc chạy unit test).
- **Build & Push**: Dùng Kaniko để build Docker Image và đảy lên DockerHub

Câu hỏi: Tại sao khi chạy Jenkins trên Kubernetes, chúng ta lại ưu tiên sử dụng Kaniko để build Docker Image thay  vì mount ```docker.sock``` (Docker in Docker)
A. Vì Kaniko chạy nhanh hơn Docker
B. Vì Kaniko không yêu cầu quyền root (privileged mode) và không phụ thuộc vào Docker daemon, giúp tăng cường bảo mật cho cluster.
C. Vì Kaniko là sản phẩm của Jenkins

B.
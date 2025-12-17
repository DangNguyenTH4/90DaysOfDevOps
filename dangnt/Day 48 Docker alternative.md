**1. Podman:**

- Đối thủ nặng ký nhất của Docker.
- **Daemonless**: Không cần một process chạy ngầm (daemon) như Docker Engine.
- **Rootless**: Có thể chạy container mà không cần quyền root (an toàn hơn).
- Lệnh y hệt Docker: ```podman run```, ```podman ```. Bạn có thể ```alias docker=podman``` và dùng như bình thường.

**2. Containerd:**

- Thực ra Docker cũng dùng Containerd bên dưới để chạy container.
- Nó là một "Container Runtime" cấp thấp hơn, tập trung vào sự đơn giản và hiệu năng. Kubernetes hiện tại dùng Containerd trực tiếp thay vì qua Docker.

**3. LXC (Linux Containers):**

- "Ông tổ" của Docker.
- Docker ban đầu được xây dựng dựa trên LXC.
- LXC giống một máy ảo siêu nhẹ (System Container) hơn là một Application Container như Docker.
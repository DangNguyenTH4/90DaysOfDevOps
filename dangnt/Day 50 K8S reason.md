Hôm nay chúng ta sẽ xem xét các cách để có được một cụm Kubernetes (Cluster) để thực hành và chạy ứng dụng.

**1. Local (Chạy trên máy cá nhân):**

- **Minikube**: Tạo một máy ảo (VM) nhỏ trên máy tính của bạn và chạy K8s trong đó. Rất phổ biến cho người mới học.
- **Kind (Kubernetes in Docker)**: Chạy K8s node dưới dạng các Docker Container. Siêu nhẹ, khởi động nhanh.
- **Docker Desktop**: Có sẵn K8s tích hợp, chỉ cần vào Setting bật lên là xong (nhưng hơi nặng).

**2. Managed Services (Dịch vụ được quản lý trên Cloud):** Các nhà cung cấp Cloud lo hết phần khó nhất (Control Plane), bạn chỉ việc chạy ứng dụng.

- **EKS** (Amazon Elastic Kubernetes Service).
- **AKS** (Azure Kubernetes Service).
- **GKE** (Google Kubernetes Engine).

**3. Bare-Metal / Self-Managed:**

- Tự cài K8s lên server vật lý hoặc VPS bằng công cụ như ```kubeadm```. Khó nhất, nhưng bạn học được nhiều nhất về cấu trúc bên trong.

**Câu hỏi:** Đối với người mới bắt đầu học Kubernetes như bạn, giải pháp nào là **nhanh nhất, rẻ nhất và dễ nhất** để có một cluster chạy ngay trên máy tính cá nhân (Laptop)? 
A. Mua 3 con server vật lý về lắp mạng LAN. 
B. Đăng ký tài khoản AWS và tạo EKS Cluster (tốn tiền). 
C. Cài đặt **Minikube** hoặc **Kind**.
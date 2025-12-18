Thực hành backup ứng dụng chạy trên Kubernestes bằng công cụ **Kassten K10**
**1. Chuẩn bị:**
- Sử dụng Minikube với các addon ```volumesnapshots``` và ```csi-hostpath-driver``` để hỗ trợ tính năng chụp ảnh ổ đĩa (snapshot).
- Cài đặt Kasten K10 bằng Heml
**2. Kịch bản thực hành**
- **Deploy ứng dụng:** Chạy một ứng dụng Pac-Man có sử dụng database MongoDB để lưu điểm cao (High Scores).
- **Backup**: Dùng Kassten K10 để tạo 1 bản snapshot cho toàn bộ ứng dụng Pac-Man (bao gồm cả cấu hình và dữ liệu trong MongoDB).
- **Gây lỗi (Failure Scenario)**: Vào game và cố tình tạo các bản ghi "tác" hoặc xóa nhầm dữ liệu điểm cao.
- **Restore**: Dùng Kassten K10 chọn bản Snapshot đã tạo trước dó và thực hiện Restore. Kết quả là ứng dụng quay về trạng thái sách sẽ ban đầu
**3.Tại sao dùng Kassten K10?**:
- Nó hiểu được cấu trức của Kubernetes (Pods, ConfigMaps, PVCs...).
- Nó có giao diện đồ họa (Dashboard) rất dễ sử dụng để lập lich backup và restore chỉ với vài cũ click.
**Câu hỏi**: Khi bản thực hiện restore moojot ứng dụng bằng Kassten K10, nó sẽ khôi phục những gì?
A. Chỉ khôi phục lại các file dữ liệu trong ổ cứng (Persistent Volume).
B. Chỉ khôi phục lại các file cấu hình YAML của Kubernetes.
C. Khôi phục toàn bộ "hệ sinh thái" của ứng dụng đó, bao gồm cả dữ liệu (Data), cấu hình (Config) và các tài nguyên liên quan ( Resources).


C
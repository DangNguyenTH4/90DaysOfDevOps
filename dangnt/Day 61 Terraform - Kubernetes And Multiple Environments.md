**1. Terraform với Kubernetes**: Thay vì dùng ```
kubectl apply -f deployment.yaml```, ta có thể dùng TF để quản lý các tài nguyên K8S (Deployment, Servie, Namespace...). Lợi ích
- Dùng chung một ngôn ngữ HCL cho cả hạ tầng (AWS/VM) và ứng dụng K8s
- Quản lý được vòng đời (Lifecycle) của ứng dụng tốt hơn.
**2. Quản lý nhiều môi trường(Multiple Environments)**: Làm sao để tạo ra 3 môi trường giống hệt nhau (Dev, Staging, Prod) mà không phải copy code ra 3 thư mục? Có 2 cách chính:
- **Terraform Workspaces**:Cùng 1 thư mục code, nhưng chuyển đổi qua lại giữa các không gian làm việc (worksspace) khác nhau. Mỗi workspace có một file state riêng.
- **File Structure (Directory Layout)**  : Chia thư mục riêng cho từng môi trường (```/dev```, ```/prod```) và dùng Module để tái sử dụng code chung. Cách nayfan toàn hơn và được khuyên dùng cho production.

Câu hỏi: Tại sao file structure (chia thư mục riêng) lại được đánh giá là an toàn hơn TF workspace cho môi trường production?
A. Vì nó chạy nhanh hơn.
B. Vì nó giúp tách biệt hoàn toàn file State(Backend Isolation), giảm nguy cơ "lỡ tay" xóa nhầm Production khi đang nghĩ mình ở "dev".
C. Vì workspaces không hỗ trợ AWS

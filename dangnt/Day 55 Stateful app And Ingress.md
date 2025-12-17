**Ngày 55: Stateful Apps & Ingress (Ứng dụng có trạng thái)**

Hôm nay là bài cuối về Kubernetes (theo lộ trình thực tế trong repo của bạn, Phase này kết thúc ở đây để chuyển sang IaC).

**1. Stateless vs Stateful:**

- **Stateless (Không trạng thái)**: Web App, API. Các Pod giống hệt nhau, chết cái này thay cái khác, không mất dữ liệu quan trọng (vì dữ liệu lưu ở DB). Dùng ```Deployment```.
- **Stateful (Có trạng thái)**: Database (MySQL, MongoDB). Mỗi Pod là duy nhất (ví dụ: Master - Slave). Nếu Pod Master chết, Pod mới sinh ra phải biết nó là Master và cần lấy lại đúng dữ liệu cũ. Dùng ```StatefulSet```.
**2. Persistent Volume (PV) & Persistent Volume Claim (PVC):**

- Container khi chết sẽ mất hết dữ liệu bên trong.
- Để lưu dữ liệu lâu dài (cho Database), ta cần **Persistent Volume** (ổ cứng mạng).
- Pod muốn dùng ổ cứng thì phải tạo một "phiếu yêu cầu" gọi là **PVC**.

**Câu hỏi:** Khi bạn triển khai một cụm Database MongoDB trên Kubernetes, bạn nên dùng loại resource nào để đảm bảo tính ổn định và định danh duy nhất cho từng Pod (ví dụ: ```mongo-0```, ```mongo-1```)? 
A. Deployment B. DaemonSet C. StatefulSet

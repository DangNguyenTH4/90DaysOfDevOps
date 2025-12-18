Là khôi phục hệ thống khi toàn bộ một trung tâm dữ liệu hoặc vùng(Region) của Cloud bị sập.

**1. Kịch bản Disaster Recovery (DR):**
- Chúng ta có Cluster chính (Primary) đang chạy ứng dụng.
- Chúng ta có Cluster dự phòng (Standby) ở một nơi hoàn toàn khác.
- Mục tiêu: Nếu CLuster chính "bay màu", chúng ta có thể dựng lại ứng dụng trên Cluster dự phòng nhanh nhất có thể.

**2. Quy trình thực hiện voiwss Kassten K10:**
- **Export**: Trên Cluster chính, chúng ta tạo Policy để không chỉ Snapshot mà còn **Export** bản backup đó ra một nơi lưu trữ bên ngoài (Ví dụ :AWS S3).
- **Import**: Trên Cluster dự phòng, chúng ta tạo một **Import Policy**l Policy này sẽ kết nối tới S3, lấy thông tin về các bản backup đã được export từ Cluster chính.
- **Restore**: Sau khi import xong, chúng tacos thể thực hiện Restore ứng dụng ngay trên Cluster dự phòng.
**3. RTO và RPO**:
- **RTO (Recovery Time Objective)**: Thời gian tối đa để khôi phục hệ thống au sự cố.
- **RPO (Recovery Point Objective):** Lượng dữ liệu tối đa chấp nhận bị mất (tính bằng thời gian, ví dụ: Backup mỗi 1 giờ thì RPO là  1 giờ).

**Câu hỏi:** Trong quy trình Disaster Recovery giữa hai Kubernetes cluster, tại sao chúng ta cần bước **Export** bản backup ra một Object Storage (như S3) thay vì chỉ lưu Snapshot tại chỗ trên Cluster chính.
A. Để tiết kiệm dung lượng ổ cứng cho Cluster chính.
B. Để bản backup nằm ở một nơi độc lập. Nếu cluster chính bị sập hoàn toàn, Cluster dự phòng vẫn có thể truy cập vào S3 để lấy dữ liệu khôi phục.
C. Vì Kassten K10 bắt buộc phải dùng S3 mới chạy được.


- **
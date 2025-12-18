Khả năng di chuyển (mobility) ứng dụng và dữ liệu giữa các môi trường khác nhau.
**1. Tại sao cần Mobility?**
- **Thay đổi hạ tầng**: Chuyển từ On-premise lên Cloud hoặc giữa các Cloud Provider khác nhau (ví dụ từ AWS sang Azure) để tối ưu chi phí.
- **Nâng cấp**: Chuyển ứng dụng từ storage chậm sang storage nhanh hơn.
- **Mở rộng**: Chuyển sang một Cluster lớn hơn để đáp ứng lượng người dùng  tăng đột biến.
**2. Tính năng Transformation (Biến đổi) của Kassten K10**:
- Khi khôi phục (Restore) một ứng dụng sang Cluster mới, ta không nhất thiết phải giữ nguyên mọi thứ. Kassten K10 cho phép thực hiện các thay đổi t rong quá trình restore:
- - **Thay đổi Storage Class**: Ví dụ chuyển từ ```slow-slorage `` sang ```fast-ssd```.
- **Thay đổi só lượng Replicas**: Ví dụ tăng từ 1pod lên 5 pods để tăng khả năng chịu tải.
- **Thay đổi cấu hình:** Cập nhất các biến môi trường (Environoment Variables) chu phù hợp với môi trường mới.

**3. Tổng kết hành trình**: Chúng ta đã đi qua một chặng đường dài từ Lnux, Go, Networking,IaC, Config Management, CI/CD, Monitoring và cuối cùng là Data Management.
**Câu hỏi**: Nếu bạn muốn di chuyển một ứng dụng từ Cluster A sang Cluster B nhưng cluster B sử dụng một loại ổ cứng khác (StorageClass khác)  so với CLuster A, bạn sẽ làm gì để ứng dụng đó có thể chạy được trên ClusterB?
A. Phải sử thủ công trong từng file YAML của ứng dụng sau khi đã restore xong.
B. Sử dụng tính năng **Transformation** của công cụ backup (như Kassten K10) để tự động đổi tên StorageClass trong quá trình restore.
C. Không thể di chuyển được nếu hai cluster khác loại ổ cứng.


- 
  ```
  ```chuyển
**Kanister**: Một framework mã nguồn mở giúp quản lý dữ liệu ở cấp độ ứng dụng (Application  level).
**1.Tại sao cần Kanister?**
- Đôi khi việc chỉ Snapshot ổ đĩa (Storage Snapshot) là chưa đủ. Với các database phức tạp, bạn cần thực hiện các lệnh cụ thể (ví dụ : ```mysqldump```) để đảm bảo dữu liệu được backup một cách toàn vẹn và nhất quán (Application Consistency).
**2. Các thành phần chính của Kanister:**
- **Blueprint:** Chứa các bước hướng dẫn cách backup và restore cho một loại database cụ thể (ví dụ: Blueprint cho Mysql, Blueprint cho PostgreSQL).
- **Profile**: Nơi lưu trữ bản backup (Thường là S3 hoặc các Object Storage khác).
- **ActionSet**: Lệnh thực thi một hành động (Backup hoặc Restore) dựa trên Blueprint.
**3. Kịch bản thực hành:**
- Deploy MySQL.
- Tạo **Profile** trỏ tới S3.
- Sử dụng **Blueprint** có sẵn cho MySQL.
- Tạo **ActionSet** để thự hiện backup (Kanister sẽ chạy lệnh ```mysqldump``` bên trong container và đẩy file lên S3).
- Xóa database và dùng ActionSet khác để restore.

**Câu hỏi:** Điểm khác biệt lớn nhất giữa việc dùng **Storage Snapshot** và **Kanister Blueprint** để backup database là gì?
A. Storage snapshot nhanh hơn nhưng Kanister đảm bảo tính nhất quản của dữ liệu ở mức ứng dụng tốt hơn (ví dụ: Đảm bảo các transaction đang dở dang được xử lỹ đúng).
B. Kanister chỉ dùng được ho MySQL, còn Storage Snapshot dùng được cho mọi thứ.
C. Storage Snapshot là miễn phí , còn Kanister là trả phí.
A
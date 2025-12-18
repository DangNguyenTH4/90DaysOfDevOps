**1. Tại sao phải Backup?**
- Không chỉ để chống lại Ransomeware hay thảm họa, lý do phổ biến nhất là **Xóa nhầm (Accidental Deletion)**.
- "High Availability" (Sẵn sàng cao) không thay thế được Backup. Nếu bạn xóa nhậm dữ liệu trên một cluster, lỗi đó sẽ được replicate sang tất cả các node ngay lập tức. Chỉ có Backup mới giúp bạn quay lại thời điểm trước khi xóa.
**2. Quy tắc 3-2-1 (Quy tắc vàng trong backup)**:
- **3:** có ít nhất **3 bản sao** dữ liệu (1 bản gốc + 2 bản backup)
- **2**: Lưu trữ trên 2 loại phương tện khác nhau (ví dụ: 1 trên ổ cứng server, 1 trên NAS hoặc băng từ).
- **1:** Có ít nhất **1 bản lưu offsite** (ở một nơi khác hoàn toàn, ví dụ: Trên cloud hoặc một trung tâm dữ liệu khác) để đề phòng thảm họa, cháy nổ tại chỗ.
**3. Công cụ thực hành:**
- **Kopia** - một công cụ backup mã nguồn mở, hỗ trợ mã hóa, nén và gửi dữ liệu lên nhiều nơi như S3, Google Cloud Storage..

Câu hỏi: Theo quy tắc **3-2-1**, nếu có 1 bản sao dữ liệu đang chạy trên server, và 1 bản sao backup trên một ổ cứng gắn ngoài, để ngay cạnh server đó, bạn còn thiếu điều gì quan trọng nhất để đảm bảo an toàn theo quy tắc này?
A. Thiếu thêm 1 bản backup nữa lưu ở một vị trí địa lý khác (Offsite)
B. Thiếu việc né dữ liệu để tiết kiệm dung lượng.
C. Thiếu việc đặt mật khẩu cho bản backup.


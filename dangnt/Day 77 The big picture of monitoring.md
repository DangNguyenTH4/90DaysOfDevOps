**1. Tại sao cần monitoring.**
- Để biết hệ thống có đang hoạt động ổn định không (Health Check).
- Để phát hiện sớm các vấn đề (ví dụ: ổ cứng sắp đầy, CPU quá tải) trước khi nó làm sập hệ thống.
- Để có cái nhìn tổng quan (40,000ft view) về toàn bộ hạ tầng
**2. Các loại monitoring:**
- **Infrastructure Monitoring:** Giám sát server (CPU, RAM, Disk,Network). Ví dụ: Nagios, Zabbix...
- **Application Monitoring:** Giám sát ứng dụng (Response time, Eror rate, Transaction).
- **Network Monitoring:** Giám sát lưu lượng mạng, switch, router.

Câu hỏi: Trong giám sát hạ tầng (Infrastructure Monitoring), nếu bạn nhận được cảnh báo rằng ổ cứng (Disk Usage) của Database Server đạt 90% và đang tăng nhanh, hành động nào sau đay là **Kém hiệu quả nhất** về mặt dài hạn?
A. Mở rộng dung lượng ổ cứng (Scale Up) hoặc dọng dẹp logfile cũ ngay lập tức để tránh sập server.
B. Tắt cảnh báo đi (Silence Alert) vì nghĩ rằng 10% còn lại dùng được lâu.
C. Tìm nguyên nhân gốc rễ (Root cause) tại sao dữ liệu tăng nhanh đột biến để có giải pháp xử lý triệt để..)
 
 
 **B**. Tắt cảnh báo là hành động "bịt tai trộm chuông", không giải quyết được vấn đề gốc rễ.
**Prometheus:** Công cụ giám sát phổ biến nhất trong thế giới Cloud Native
**1. Prometheus là gì?** 
- Là hệ thống giám sát mã nguồn mở (Open Source Monitoring System)
- Chuyên dùng để giám sát các hệ thống microserrvices và container (như Kubernetes).
**2. Cơ chế hoạt động (Pull Model)**
- Khác với các hệ thống giám sát truyền thống (Push Model - Server tự đẩy log về), Prometheus hoạt động theo cơ chế **Pull**.
- Prometheus Server sẽ định kỳ "kéo" (Scrape) các thông số (metrics) từ các ứng dụng/server đích thông qua một endpoint HTTP (thường là ```metric```)
**3.Thành phần chính:**
- **Prometheus Server**: Thu thập và lưu trữ metrics.
- **Exporters:** Các "đại sứ" giúp chuyển đổi metrics của hệ thống (Linux, Mysql, Nginx...) sang định dạng mà Prometheus hiểu được.
- **AlertManager**: Quản lý và gửi cảnh báo (Qua Email,Slack...).
- **PromQL:** Ngôn ngữ truy vẫn mạnh mẽ để lấy dữ liệu từ Prometheus.

**Câu hỏi:** Tại sao Prometheus lại ưu tiên sử dụng cơ chế **Pull** (Server chủ động kéo dữ liệu) thay vì **Push**(Clien đẩy dữ liệu về)?
A. Vì cơ chế pull giúp Prometheus dễ dàng kiểm soát tần suất lấy dữ liệu và phát hiện ngay nếu một service bị chết (Không kéo được dữ liệu). 
B. Vì cơ chế **Push** làm tốn băng thông mạng hơn.
C. Vì cơ chế Pull bảo mật hơn tuyệt  đối so với Push.

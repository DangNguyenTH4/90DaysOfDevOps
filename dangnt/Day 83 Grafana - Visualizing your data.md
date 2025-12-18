Grafana công cụ vẽ biểu đồ quyền lực nhất trong giới devops
**1. Grafana là gì?**
- Là nền tảng mã nguồn mở chuyên về **Visualization** (trực quan hóa dữ liệu) và **Analytics.**
- Grafana không tự lưu trữ dữ liệu. Thay vào đó, nó kết nối tới các **Data Sources** (như prometheus, elasticsearch, influxDB) để lấy dữ liệu và hiển thị lên các Dashboard lung linh.

**2. Tại sao dùng Grafana?**
- **Dashboard đẹp và linh hoạt:** Chúng ta có thể tạo các biểu đồ đường, cột, bản đồ nhiệt (heatmap), đồng hồ đo (gause)... cự kỳ chuyên nghiệp.
- **Hỗ trợ đa nguồn:** Bạn có thể hiển thị metrics từ Prometheus và log từ Prometheus và log từ Elasticsaerch trên cùng một dashboard duy nhất.
- **Alerting**: Gửi cảnh báo khi các chỉ số vượt ngưỡng (Ví dụ: CPU >90% trong 5 phút).

**3. Triển khai:**
- Thường được cài đặt bằng Docker hoặc Help Chart trên kubernetes.
- Sau khi cài đặt, bạn chỉ cần add "Data source" (Ví dụ địa chỉ của Prometheus server) là có thể bắt đầu vẽ biểu đồ.

**Câu hỏi:** Điểm khác biệt cơ bản nhất giữa **Prometheus** và **Grafana** là gì?
**A**. Prometheus dùng để lưu trữ và truy vấn dữ liệu (metrics), còn Grafana dùng để hiển thị đữ liệu đó lên các Dashboard trực quan.
**B**. Prometheus chỉ dùng được cho Linux, còn Grafana dùng được cho mọi OS
**C**. Prometheus là công cụ trả phí, còn Grafana là miễn phí.

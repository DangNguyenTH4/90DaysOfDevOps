Một giải pháp thay thế cho logstash/filebeat trong hệ sinh thái Kubernetes. **Fluentd và FluentBit** (EFK)
**1. Fluentd là gì?**
- Là một "Unified Logging Layer" (Lớp thu thập log thống nhất).
- Nó gom log từ nhiều nguồn, chuyển sang định dạng JSON và fđẩy đi nhiều nơi (Elasticsearch, S3, Kafka...).
- Có hơn 1000plugins để kết nối với đủ loại hệ thống.
**2. FluentBit là gì?**
- Là phiên bản siêu nhẹ của Fluentd, viết bằng ngôn ngữ C.
- Trong Kubernetes, FluentBit thường được triển khai dưới dạng **DaemonSet** (Mỗi node chạy 1 pod) để thu thập log từ tất cả các container trên node đó.
- Nó cực kỳ hiệu quả về bộ nhớ (Chỉ tốn vài MB Ram)
**3. So sánh nhanh:**
- **Fluentd:** Mạnh mẽ, nhiều plugin, tốn nhiều RAM hơn (viết bằng Ruby/C).
- **FluentBit:** Siêu nhẹ, ít plugin hơn, cự kỳ phù hợp cho môi trường Edge hoặc Container (Viết bằng C).

**Câu hỏi:** Trong một Kubernetes cluster có hàng trăm node, bạn muốn thu thập log từ tất cả các container mà không làm ảnh hưởng nhiều ddeens tài nguyên (RAM/CPU) của các node đó. Bạn nên chọn công cụ nào để cài đặt lên từ node?
A. Fluentd
B. FluentBit
C. Logstash (Chạy trực tiếp trên từng node)

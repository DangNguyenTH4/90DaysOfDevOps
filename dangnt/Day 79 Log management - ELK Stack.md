Hôm nay chúng ta sẽ tìm hiểu về quản lý Log tập trung, một mảnh ghép quan trọng khác của Obserrvability.
**1. Log Aggregation (Thu thập Log tập trung)**:
- Thay vì phải SSH vào từng server để đọc file log(```tail -f /var/log/nginx/access.log```), chúng ta gom tất cả log từ hàng trăm server về một nơi duy nhất để dễ tìm kiếm và phân tích.
**2. ELK Stack:** Bộ công cụ nổi tiếng nhất cho việc log tập trung là **ELK** đối với cloud có thể sẽ dùng **EFK**
- **E - Elasticsearch**: Database chuyên dụng để lưu trữ và tìm kiếm văn bản (text search engine). Log sẽ được lưu ở đây.
- **L - Logstash:** Công cụ thu thập (Collect), xử lý (Process/Parse) và chuyển tiếp (Forward) log. Ví dụ: Logstash đọc log từ file, tách các trường (IP, Time, URL, Status Code) rồi đẩy vào Elasticsearch.
- **K - Kibana**: Giao diện Web (Dashboard) để hiển thị và tìm kiếm log từ Elassticsearch.
*Lưu ý: Ngày nay thường dùng Fluentd, Filebeat, Fluentbit thay cho Logstash vì nhẹ hơn*.
Câu hỏi: Trong bộ ELK Stack, thành phần nào đóng vai trò là "Giao diện người dùng" (UI), nơi bạn truy cập vào để gõ từ khóa tìm kiếm lỗi ( ví dụ: "Error 500") và xem biểu đồ số lượng lỗi theo thời gian?
A. Elasticsearch
B. Logstash
C. Kibana

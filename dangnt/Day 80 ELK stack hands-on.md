Triển khai ELK Stack bằng docker compose:
**1.Triển khai**
- Sử dụng ```docker-compose``` để chạy 3 container Elasticsearch, Logstash, Kibana.
- Cấu hình logstash để nhận dữ liệu input đẩy vào Elasticsearch (output)
**2.Beats:**
- Ngoài logstash, hệ sinh thái Elastic còn có **Beats:** các agent siêu nhẹ (lighweight data shipper) cài trên các server đích để gửi dữ liệu về Logstash hoặc Elasticsearch
- Ví dụ:
	- **File beat:** Gửi log file
	- **Metricbeat:** Gửi metrics (CPU, RAM)
	- **Packetbeat:** Gửi dữ liệu gói tin mạng.

Câu hỏi: Trong môi truowngfthuwjc tế, tại sao người tathuowngf cài **Filebeat** trên từng server để thu thập log thay vì cài **Logstash** trên từng server?
**A**. Vì Filebeat nhẹ hơn rất nhiều (viết bằng Go) so với Logstash (Viết bằng Java/Ruby), giúp tiết kiệm tài nguyên cho server ứng dụng.
**B**. Vì Filebeat có nhiều tính năng xử lý log mạnh mẽ hơn logstash.
**C**. Vì Logstash khoong thể cài trên Linux.

A
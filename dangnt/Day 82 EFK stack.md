Triển khai bộ 3 EFK lên kubernetes (Minikube)
**1. Tại sao lại là EFK thay vì ELK?**
- Trong môi trường Kubernetes, **Fluentd** hoặc **FluentBit** được ưa chuộng hơn Logstash vì nó nhẹ hơn và có khả năng tự động thu thập log từ tất cả  các container thông qua cơ chế **DaemonSet**.
- **Elasticsearch** vẫn đóng vai trò lưu trữ.
- **Kibana** vẫn đóng vai trò hiển thị.
**2. Triển khai trên kubernetes:**
- **Elasticsearch:** triển khai dưới dạng **StatefulSet** (vì cần lưu trữ dữ liệu bền vững).
- **Fluentd:** Triển khai dưới dạng **DaemonSet** (Để đảm bảo mỗi node đều có 1 pod thu thập log)
- **Kibana**: Triển khai dưới dạng **Deployment**

Câu hỏi: Khi triển khai Fluentd trên Kubernetes dưới dạng **DaemonSet**, mục đính chính của việc này là gì?

A. Để đảm bảo rằng trên mỗi Node của Cluster đều có đúng một Pod Fluentd chạy để thu thập log từ tất cả các container trên Node đó.
B. Để Fluentd có thể tự dộng mở rộng (Scale) số lượng pod khi log tăng nhiều
C.  Để tiết kiệm địa chỉ IP cho Cluster
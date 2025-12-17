1. **Development (Phát triển)**: Lên kế hoạch, viết code. Đây là nơi các Developer làm việc chính.
2. **Testing (Kiểm thử)**: Code sau khi viết xong phải được test. Trong DevOps, chúng ta hướng tới **Automated Testing** (kiểm thử tự động) để phát hiện lỗi sớm nhất có thể.
3. **Integration (Tích hợp)**: Code được merge (gộp) vào kho code chung thường xuyên (CI - Continuous Integration). Mỗi lần merge đều kích hoạt test tự động.
4. **Deployment (Triển khai)**: Đưa ứng dụng lên môi trường Production (CD - Continuous Deployment/Delivery). Đây là lúc Infrastructure as Code (IaC) và Container (Docker/K8s) tỏa sáng.
5. **Monitoring (Giám sát)**: Sau khi chạy, phải theo dõi xem ứng dụng có khỏe không, người dùng có hài lòng không. Feedback từ đây sẽ quay lại bước Development để cải tiến sản phẩm.
**Điểm mấu chốt**: Mọi thứ diễn ra liên tục (Continuous) - Continuous Development, Continuous Testing, Continuous Integration, Continuous Deployment, Continuous Monitoring.

**Câu hỏi ôn tập:** Tại sao **Monitoring** (Giám sát) lại quan trọng và nó liên quan gì đến bước đầu tiên (Development) trong vòng lặp này?
--> Monitoring để liên tục nhìn thấy vấn đề và cải tiến nó. Và chắc chắn nó liên quan tới bước đầu tiên để automation sau khi phát triển xong 1 tính năng, để sớm phát hiện ra vấn đề tự động và cải tiến
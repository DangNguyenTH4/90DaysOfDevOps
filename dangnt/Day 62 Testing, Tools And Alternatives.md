**1. Testing & Code Quality**: Code hạ tàng cũng cần được kiểm tra như code phần mềm.
- ```terraform fmt``` : Tự động format code cho nó đẹp, đúng chuẩn
- ```terraform validate``` : kiểm tra lỗi cú pháp (syntax eror).
- **TFLint**: một công cụ bên ngoài (linter) giúp tìm các lỗi logic, cánh báo về các cú pháp cũ (deprecated).
- **Checkov / tfsec**: Quyets lỗ hổng bảo mật ( ví dụ : bạn lở mở port 22 cho cả thế giới, hoặc để lộ Access Key).
**2. Các giải pháp thay thế Terraform**:
- **Pulumi**: Cho phép bạn viết IaC bằng ngôn ngữ lập trình thật sự (Python, TypeScript, Go...) thay vì HCL. Rất mạnh nếu bạn là developer.
- **CloudFormation (AWS)/ ARM Templates (Azure)**: Công cụ "chính chủ" của cloud provider. Tốt nhưng bị khóa chặt vào cloud đó (Vendor Lock-In).

Câu hỏi: Bạn muốn tích hợp một bước kiểm tra bảo mật vào quy trình CI/CD để đảm bảo không ai có thể deploy một server AWS S3 Bucket ở chế đồ "Public Read" . Công cụ nào sau đay phù hợp nhất?
A. ```terraform fmt```
B. ```terraform plan```
C. ```tfsec``` hoặc ```Checkov```

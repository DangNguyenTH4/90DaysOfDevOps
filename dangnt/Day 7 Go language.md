*Tại sao phải học GO*
1, Ngôn ngữ của cloud & devops: Hầu hết các công cụ khủng của devops đều viết bằng Go: Docker, Kubernetes, Prometheus, Teraform, Grafana
 -> Học go giuips đọc hiểu mã nguồn của các công cụ này (Lợi thế khi cần debug sâu)
 2, Hiệu năng cao & dễ deploy
  - Go biên dịch ra 1 file chạy duy nhất ( Single binary). Chỉ cần copy file này sang server nào cũng chạy được ngay, không cần cài thư viện lằng lằng như python hay java
  - Tốc độ xử lý rất nhanh, gần bằng C/C++.
  3, Concurrency ( Xử lý đồng thời): Go sinh ra d dể xử lý hàng ngàn tác vụ cùng lúc (Rất hợp với cloud/ microservice )
  Mục tiêu của chúng ta: Không phải để trở thành Go Developer chuyện nghiệp viết app bán hàng, mà là để viết các tool tự động hóa, script quản lý hệ thống, và hiểu sauau về Kubernetes sau này.
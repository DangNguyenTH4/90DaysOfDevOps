**Terraform là gì?**
- Là công cụ giúp bạn khai báo hạ tầng ( Server, Network, DNS...) bằng code.
- Cloud Agnostic : Nó chơi được với t ất cả các Cloud lớn (AWS, Azure, GDC) và cả On-premise(VM-ware , Openstack). Bạn học 1 công cụ, dùng được cho mọi nơi.
**Quy trình làm việc (Workflow) của terraform** gồm 3 bước chính.
1. Write: viết file cấu hình (đuôi .tf) mô tả hạ tầng bạn muốn.
2. Plan: Chạy ```terraform plan```. Nó sẽ so sánh code của bạn với thực tế và nói "Tôi sẽ tạo thêm 2 server, xóa 1 db..." bạn có đòng ý không?". Bước này giúp kiểm tra trước khi làm thật (Dry run)
3. Apply: Chạy ```terraform apply``` . Lúc này nó mới thực sự tác động lên Cloud để tạo/xóa tài nguyên.
Câu hỏi:
Điểm manh lớn nhất của Teraform so với các công cụ cloud specific như AWS cloudformation hay Azure Resource Manager) Là gì?
A Terraform chạy nhanh hơn
B. Terraform được chính AWS phát triển.
C. Terraform là Cloud Agnostic, có thể dùng chung một quy trình và ngôn ngữ để quản lý hạ tầng trên nhiều nhà cung cấp Cloud khác nhau (AWS , Azure, GCP...).



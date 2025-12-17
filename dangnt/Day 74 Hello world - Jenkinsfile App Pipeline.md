Trong phần này sẽ hoàn thiện pipeline bằng cách kết nối Jenkins với github.
**1. Pipeline from SCM (Source Code Management):**
- Thay vì copy-paste nội dung ```Jenkinsfile``` vào giao diện Jenkins (cách làm thủ công),, chúng ta sẽ cấu hình Jenkisn để nó tự động lấy file ```Jenkinsfile``` từ Github repository
- Lợi ích: Quản lý phiên bản (Version Control) Cho cẩ Pipeline. Ai sửa Pipeline đều lưu lại lịch sử.

**2.Triggers (Kích hoạt tự động):**
- Làm sảo để khi Developer push code lên Github, Jenkisn tự động chạy build?
     -  **Poll SCM:** Jenkins định kỳ (ví dụ 5min/time) hỏi Github : "Có gì mới không?" . Nếu có thì chạy. (Tốn tài nguyên, chậm)
	  - **Git hub webhook**: GitHub chủ động báo cho Jenkins ngay lập tức khi có code mới. (Nhanh, hiệu quả, nhưng càn Jenkins có public IP hoặc cấu hình mạng để GitHub gọi tới được).
Câu hỏi:  Trong môi trường Production thực tế, phương pháp nào được ư tiên sử dụng để kích hoạt Jenkins Pipeline ngay khi có code mới được push lên Github?
A. Poll SCM (Hỏi định kỳ).
B. Github Webhook (GitHub báo ngay lập tức) .
C. Chảy thủ công bằng nút "Build Now".



**1. Vấn đề "It works on my machine":**

- Code chạy ngon trên máy Dev (Windows), nhưng đem lên Server (Linux) thì lỗi tùm lum do thiếu thư viện, sai phiên bản, xung đột phần mềm...
- Giải pháp cũ: Máy ảo (Virtual Machine - VM). Cài nguyên một cái hệ điều hành (OS) mới cho mỗi ứng dụng. -> Nặng, chậm, tốn tài nguyên.

**2. Giải pháp Container:**

- Container đóng gói **Code + Mọi thứ nó cần để chạy** (thư viện, cấu hình...) vào một cái hộp kín.
- Cái hộp này đem đi đâu cũng chạy y hệt nhau (trên Laptop, trên Server, trên Cloud).
- **Nhẹ hơn VM rất nhiều**: Vì các Container dùng chung nhân (Kernel) của hệ điều hành máy chủ, không cần cài lại cả cái OS cho mỗi container.

**3. Image vs Container:**

- **Image**: Là cái khuôn đúc (File tĩnh, không thay đổi). Ví dụ: Đĩa cài Win.
- **Container**: Là cái bánh được đúc từ khuôn (Phiên bản đang chạy). Ví dụ: Windows đang chạy trên máy bạn.
- Từ 1 Image có thể tạo ra hàng nghìn Container chạy giống hệt nhau.

**Câu hỏi:** So sánh với Máy ảo (Virtual Machine), ưu điểm lớn nhất của Container là gì? A. Container bảo mật tốt hơn VM. B. Container nhẹ hơn và khởi động nhanh hơn vì không cần hệ điều hành riêng (Guest OS) cho mỗi ứng dụng. C. Container có giao diện đồ họa đẹp hơn.
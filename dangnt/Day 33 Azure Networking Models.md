Hôm nay chúng ta nói về Mạng trên Azure.

**1. Virtual Network (VNet):**

- Là mạng riêng ảo của bạn trên Cloud.
- Giống như bạn kéo dây mạng LAN ở nhà, nhưng ở đây là trên Cloud.
- Bạn chia VNet thành các **Subnet** nhỏ hơn (ví dụ: Subnet cho Web, Subnet cho Database).

**2. Network Security Group (NSG):**

- Là Firewall (Tường lửa) cơ bản.
- Quy định ai được vào, ai được ra.
- Ví dụ: "Chỉ cho phép IP của công ty truy cập vào Server qua cổng SSH (22)".

**3. Load Balancer:**

- **Azure Load Balancer (Layer 4)**: Chia tải dựa trên IP và Port (TCP/UDP). Nhanh, rẻ, nhưng "ngu" (không hiểu nội dung gói tin).
- **Application Gateway (Layer 7)**: Chia tải thông minh hơn (HTTP/HTTPS). Có thể chia tải dựa trên URL (ví dụ: ```/images```vào Server A, ```/video```vào Server B). Có tích hợp Web Application Firewall (WAF) để chống hack.

**Câu hỏi:** Bạn có một Website bán hàng. Bạn muốn chặn tất cả các truy cập từ nước ngoài (Geo-blocking) và chặn các cuộc tấn công SQL Injection. Bạn nên dùng dịch vụ Load Balancing nào? 
A. Azure Load Balancer B. Application Gateway C. Traffic Manager
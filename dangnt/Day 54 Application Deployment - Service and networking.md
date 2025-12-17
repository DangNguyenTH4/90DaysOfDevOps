Hôm nay chúng ta sẽ học cách đưa ứng dụng ra ngoài Internet để người dùng truy cập.

**1. Service:** Pod có IP, nhưng IP đó thay đổi liên tục. **Service** sinh ra để cung cấp một địa chỉ ổn định để truy cập vào nhóm Pod. Có 3 loại Service chính:

- **ClusterIP** (Mặc định): Chỉ truy cập được từ _bên trong_ Cluster. Dùng cho Database, Backend nội bộ.
- **NodePort**: Mở một cổng (ví dụ 30000) trên _tất cả các Node_. Bạn truy cập qua ```IP_Node:30000```. Dùng để test nhanh.
- **LoadBalancer**: Dùng khi chạy trên Cloud (AWS, Azure). Cloud sẽ cấp cho bạn một Public IP thật để truy cập từ Internet.

**2. Ingress:** Service LoadBalancer rất tốn tiền (mỗi service 1 IP). **Ingress** giống như một cái Router thông minh. Nó dùng 1 IP duy nhất nhưng có thể trỏ đến nhiều Service khác nhau dựa trên tên miền (ví dụ: ```api.web.com``` -> Service API, ```shop.web.com``` -> Service Shop).

**Câu hỏi:** Bạn có một Web App chạy trên K8s. Bạn muốn người dùng truy cập nó từ Internet. Cách nào sau đây là **tiết kiệm và chuẩn nhất** cho môi trường Production (thay vì dùng NodePort hay tạo hàng chục cái LoadBalancer)? 
A. Dùng **ClusterIP** và SSH vào server để xem. 
B. Dùng **Ingress Controller** để điều hướng traffic từ một Public IP duy nhất vào các Service bên trong. 
C. Mở cổng NodePort 30000 cho tất cả mọi người truy cập.

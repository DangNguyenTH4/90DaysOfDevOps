Hôm nay là ngày cuối của Phase Cloud. Chúng ta sẽ tổng hợp lại kiến thức bằng các bài Lab thực tế (dựa trên chứng chỉ **AZ-104: Azure Administrator**).

**Kịch bản 1: Virtual Networking**

- Tạo một VNet.
- Tạo 2 VM nằm trong VNet đó.
- Cấu hình để 2 VM ping thấy nhau (Private IP).
- Cấu hình để 1 VM có thể truy cập từ Internet (Public IP).

**Kịch bản 2: Traffic Management**

- Dựng mô hình **Hub-Spoke**:
    - **Hub VNet**: Chứa Firewall, VPN Gateway (Trung tâm điều khiển).
    - **Spoke VNet 1**: Chứa Web Server.
    - **Spoke VNet 2**: Chứa Database.
- Dùng **VNet Peering** để nối Spoke về Hub.

**Kịch bản 3: Web App (PaaS)**

- Deploy một Website lên **Azure App Service** (không cần tạo VM).
- Tạo **Deployment Slot**:
    - Slot "Staging": Để test code mới.
    - Slot "Production": Web đang chạy thật.
- Tính năng **Swap**: Khi test xong ở Staging, bấm nút Swap một phát là code Staging nhảy sang Production ngay lập tức (Zero Downtime).

**Tổng kết Phase 4 (Cloud):** Chúng ta đã đi qua:

- Cloud Basics (IaaS, PaaS, SaaS).
- Azure Core (Region, AZ, Resource Group).
- Security (Azure AD, RBAC, NSG).
- Compute (VM, VMSS, App Service).
- Storage (Blob, File, SQL, Cosmos DB).
- Networking (VNet, Load Balancer).

**Câu hỏi cuối cùng của Phase này:** Trong kịch bản Web App, tại sao chúng ta nên dùng tính năng **Deployment Slot** thay vì deploy thẳng code mới lên Production? A. Để tiết kiệm chi phí. B. Để có thể test kỹ trên môi trường giống hệt Production và switch qua lại tức thì nếu có lỗi. C. Để tăng tốc độ website.
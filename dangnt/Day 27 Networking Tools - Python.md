Paramiko
- Thư viện cơ bản nhất để tạo kết nối SSH trong python
- Giống như dùng PuTTy nhưng bằng code
- Hơi khó dùng vì phải xử lý nhiều thứ thủ công (như chờ thiết bị phản hồi)
Netmiko
- Được xây dựng dựa trên Paramiko nhưng "khôn" hơn.
- Nó biết cách nói chuyện với từng hãng (Cisco, Juniper, Arista...).
- Ví dụ: Cisco cần lệnh "enable" để vào chế độ admin, Netmiko tự làm luôn cho bạn
Napalm
 - Cao cấp hơn nữa. Nó giúp lấy thông tin từ nhiều hãng khác nhau nhưng trả về cùng một định dang (JSON)
 - Ví dụ lấy thông tin BGP từ Cisco và Juniper, Napalm sẽ trả về kết quả giống hệt nhau để dễ xử lý.

**Tổng kết Phase 3 (Networking)**
- Cơ bản : IP, Switch, Router
- OSI model
- DNS, DHCP, ARP, HTTP
- Automation by : Python, Ansible, Netmiko


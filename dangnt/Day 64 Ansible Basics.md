**1. Control Node & Managed Nodes:**
- Control node : máy tính cài Ansible (thường là Linux). Đây là noi bạn gõ lệnh.
- Managed Nodes: Các server mà bạn muốn điều khiển. Không cần cài gì cả, chỉ cần mở SSH
**2. Inventory (Danh sách server)**
- Ansible cần biết nó sẽ điều khiển ai. Danh sách này nằm trong file /etc/ansible/hosts ( hoặc file riêng do bạn tạo).
- Bạn có thể gom nhóm server:
```ini
[webservers]
192.168.1.10
192.168.1.11

[dbservers]
192.168.1.20
```
**3.Ad-hoc Commands:**
- Là ccs lệnh chạy nhanh, dùng 1 lần (không lưu lại).
- Ví dụ: ```ansible webservers -m ping``` (Ping tất cả server trong nhóm webservers)
- Ví dụ ```ansible all -a "free -h"``` (Kiểm tra RAM của tất cả server).

**Câu hỏi**:
Để Ansible có thể kết nói và điều khiển được các managed node (linux), điều kiện tiên quyết quan trọng nhất về mặt mạng và xác thự là gì?
A. Phải cài đặt python agent trên managed 
B. Phải mở port 80(http) trên managed nodes.
C. Phải thiết lập kết nối SSH (Tốt nhất là dùng SSH key không mật khẩu) từ Control Node tới Managed Nodes.

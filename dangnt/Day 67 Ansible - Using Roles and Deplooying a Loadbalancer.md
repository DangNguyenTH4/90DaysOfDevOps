Hôm nay chúng ta sẽ áp dụng Roles vào thực tế để triển khai một hệ thống hoàn chỉnh gồm: Web Servers, Load Balancers
**1.Common Role**
- Tạo một role tên là ```common``` để cài các gón phần mềm chung cho tất cả server (ví dụ: ```neofetch, tree, vim```).
- Role này sẽ được gọi trong mọi Playbook.
**2.Nginx Role (Load Balancer)**
- Tạo role ```nginx``` để cài đặt và cấu hình Nginx làm loadbalancer
- Cấu hình nginx sẽ trỏ traffic về 2 Web Server (web01, web02) mà ta đã tạo hôm trước.

**3.Playbook tổng hợp**```(playbook4.yaml)```:
```yaml
- hosts: webservers
  roles:
	- common
    - apache2 
- hosts: proxy (loadbalancer)
  roles:
	- common
    - nginx
      
```
Chỉ cần chạy 1 lệnh ```ansible-playbook playbook4.yaml```, toàn bộ hệ thống sẽ được cài đặt từ A-Z.

Câu hỏi: Trong kiến trúc Load Balancer với Nginx mà chúng ta vừa triển khai, Nginx đóng vai trò là gì?
A. Forward Proxy (Giấu danh tính Client).
B. Reverrse Proxy (Đứng trước Web Server, nhận request từ Client và phân phối cho các web server phias sau).
C. Database Server.

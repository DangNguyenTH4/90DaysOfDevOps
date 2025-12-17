Học tổ chức code Ansible sao cho chuyên nghiệp
**1. Tạo sao cần Roles**
- Nếu viết tất cả task vào một file ```playbook.yml``` nó sẽ dài cả ngìn dòng, rất khó quản lý
- **Role** giúp chia nhỏ playbook thành các mục con theo chức năng:
	- ```task/```: Chứa các công việc chính.
	- ```handlers/```: chứa handlers (restart service)
	- ```template/``` : chứa file cấu hình mẫu.
	- ```vars/``` : chứa biến.
-  Ví dụ: Bạn tạo một role tên là ```apache2``` chỉ chuyên cài web server, role ```mysql``` chỉ chuyên cài database
**2. Ansible Galaxy**
- Là một kho lưu trữ (repository) khổng lồ các Roles do cộng đồng đóng góp
- Bạn muốn cài Jenkins? Đừng viết code từ đầu. Lên Galaxy tìm role ```geerlingguy.jenkins```, tải về và dùng luôn.
- Lênh tạo cấu trúc Role chuẩn : ```ansible-galaxy init ten_role_moi```.

Câu hỏi:: Lệnh nào sau đây được sử dụng để khởi tạo một cấu trúc thư mục chuẩn cho một Ansible Role mới (Bao gồm các thư mục con như tasks, handlers, vars...)? 
A. ```ansible-playbook create role```
B. ``` ansible-galaxy init role_name```
C.```ansible-role --new role_name```

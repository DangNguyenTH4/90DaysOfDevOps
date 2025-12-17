**1.Playbook là gì**
- Nếu Ad-hoc command là những câu lệnh rời rạc, thì playbook là môt file YAML chữa hàng loạt các task (công  việc) cần làm theo thứ  tự.
- Cấu trúc: Playbook > Plays > Tasks
**2.Ví dụ Playbook** ```(webserver.yaml)```
```yaml
- hosts: webservers # Áp dụng cho nhóm webserver
  become: yes # Chỉ chạy với quyền root
  tasks:
	- name: cài đặt apache 
	  apt:
		name: apache2
		state: latest
		
	- name: start apache 
	  service:
		name: apache2
		state: started
		
```
Chạy playboook: ```ansible-playbook webserver.yaml```
**3.Handlers**:
- Đôi khi bạn chỉ muốn chạy 1 task khi có sự thay đổi ( ví dụ: Restart Apache chỉ khi file config bị sửa)
- **Handlers** là những gì task đặc biệt, chỉ chạy khi được một task khác "thông báo"

Câu hỏi: Trong Ansible Playbook, từ khóa nào được dùng để kích hoạt một **Handlers** chạy (ví dụ : restart service) sau khi một task thay đổi cấu hình thành  công?
A. trigger
B. call
C. notify

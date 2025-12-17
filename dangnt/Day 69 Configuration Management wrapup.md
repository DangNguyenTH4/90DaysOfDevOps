Điểm lại những công cụ trong hệ sinh thái ansible trước khi kết thúc phase 9.
**1.Ansible AWX / Automation Controller Tower**
- Ansible CLI (dòng lệnh) rất tốt cho cá nhân, nhưng khi làm việc nhóm (team), bạn cần một giao diện Web(UI) để quản lý.
- **AWX** (Opensource) hoặc **Automation controller** (Enterprise - trước đay là Ansible Tower) cung cấp
	- UI : giao diện trực quan.
	- RBAC: Phân quyền ai được chạy playbook nào.
	- Scheduling: Lên lịch chạy playbook tự động
	- History: Xem lại lịch sử chạy.
**2.Ansible Vault:**
- Giúp mã hóa (encrypt) các dữ liệu nhạy cảm như mật khẩu database, api key ... trong file YAML.
- Lệnh: ```ansible-vault encrypt secret.yml```

Câu hỏi: Bạn đang làm việc trong 1 team DevOps lớn. Bạn muốn có một nơi tập trung để quản lý các Ansible Playbook, phân quyền cho Developer chỉ được chạy một số playbook nhất định để deploy lên môi trường Dev, và xem lại lịch sử ai đã chạy cái gì vào lúc nào. Công cụ nào sau đay là phù hợp nhất?
A. Ansible CLI (dòng lệnh thuần tú)
B. Ansible Galaxy
C. Ansible AWX (hoặc red hat ansible automation controller)
C
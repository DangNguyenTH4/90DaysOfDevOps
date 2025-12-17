Những công cụ làm cho playbook linh hoạt hơn
**1.Tags**
- Khi playbook quá dài (cài web, cài db, cài proxy...), bạn không muốn chạy hết từ đàu đến cuối mỗi khi sửa một tí tẹo.
- Tags giúp bạn gắn nhãn cho từn task hoặc role
- Ví dụ: ```ansible-playbook playbook.yml --tags "database"``` --> chỉ chạy các task liên quan đến Database.
**2. Variables &  Ansible Facts**
- **Variable**: biến do người dùng định nghĩa (ví dụ: http_pport: 8080). Nên tách ra file riêng (group_vars/all.yml) để dễ quản lý.
- **Ansible Fact**: Biến do Ansible tự thu thập từ server đích (ví dụ : IP address, OS version, CPU cores...).
- Ví dụ: Dùng Facts để tự động điền IP của các web server vào file cấu hình của Load Balancer.

Câu hỏi: Bạn có một playbook lớn, cấu hình toàn bộ hệ thống. Bạn vừa sửa lại file cấu hình của nginx và chỉ muốn chạy lại các task liên quan đến nginx mà không muốn Ansible tốn thời gian kiểm tra lại database hay web server.
Bạn nên dùng tính năng nào?
A. ```ansible-playbook --skip-tags "nginx"```
B. ```ansible-playbook --limit "nginx"```
C. ```ansible-playbook --tags "nginx"``` (với điều kiện đã gắn tags nginx cho các task tương ứng.)
```
```
```
  ```
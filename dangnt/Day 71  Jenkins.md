Ông trùm trong làng CI/CD
**1. Jenkins là gì?**
- Là một automation server mã nguồn mở (Open source), viết bằng Java
- Nó giúp tự động hóa các quy trình phát triển phần mềm như Build/Test/Deploy.
- Jenkins cực kỳ phổ biến nhờ hệ thống plugin khổng lồ (hơn 1800 plugins), giúp nó kết nối được với hầu hết các công cụ khác (Git, Dockers, Kubernetes, Slac, Jira...).
**2. Kiến trúc của Jenkins:**
- Master-Slave (Controller - Agent):
	- Master (Controller): Quản lý job, lên lịch, theo dõi trạng thái, phân phối công việc.
	- Slave(Agent): Là các máy (Node) thực sự thực hiện công việc (Build code, chạy test). Điều này giúp Jenkinscos thể build song song trên nhiều môi trường khác nhau (Windows, Linux, MacOS)
Câu hỏi: Trong kiến trúc Jenkins, tại sao chúng ta nên sử dụng mô hình **Distributed Builds** (master-slave/controller-agent) thay vì chạy tất cả mọi thứ trên một máy master Duy nhất?
A. Để tiết kiệm điện năng
B. Để giảm tải cho master, tắc  tốc độ build (chạy song song), và có thể build trên nhiều môi trường OS khác nhau (ví dụ: Build app iOS trên Mac agent, build app .NET trên Windows agent)
C. Vì master không có khả năng chạy build job.



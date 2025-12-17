Hôm nay chúng ta bàn về 2 vấn đề quan trọng: Mạng và Bảo mật cho Container.

**1. Docker Networking:** Khi bạn cài Docker, nó tự tạo ra một mạng ảo tên là ```bridge```.

- Mặc định, các container sẽ nối vào mạng ```bridge```này.
- Chúng có thể nhìn thấy nhau qua IP, nhưng **không thể** gọi nhau bằng tên (DNS Name) trừ khi bạn tạo một mạng riêng (User-defined bridge network).
- Lệnh: ```docker network create my-net```. Sau đó khi chạy container thêm ```--network my-net``` vào. Lúc này container A có thể ping container B bằng tên ```ping B```.

**2. Docker Security (Bảo mật):**

- **Đừng chạy với quyền Root**: Mặc định container chạy với quyền cao nhất (root). Nếu hacker chiếm được container, họ có thể phá hoại máy chủ.
- **Dùng Image tin cậy**: Chỉ dùng Official Image hoặc Image từ nguồn uy tín.
- **Giữ Image nhỏ gọn (Lean)**: Image càng nhỏ, càng ít phần mềm thừa thì càng ít lỗ hổng bảo mật. Đừng cài những thứ không cần thiết (như ```vim```, ```curl```...) vào image chạy production.

**Câu hỏi:** Tại sao chúng ta nên tạo một mạng riêng (User-defined network) cho các container trong cùng một ứng dụng thay vì dùng mạng mặc định ```bridge```? 
A. Để mạng chạy nhanh hơn. 
B. Để các container có thể gọi nhau bằng tên (Service Discovery) thay vì phải nhớ IP (IP có thể thay đổi mỗi khi khởi động lại). 
C. Để hacker không thể truy cập vào container.
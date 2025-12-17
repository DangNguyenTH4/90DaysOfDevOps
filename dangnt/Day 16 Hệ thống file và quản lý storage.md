Hôm nay chúng ta sẽ "mổ xẻ" cấu trúc thư mục của Linux và cách quản lý ổ đĩa.

**1. Cấu trúc thư mục (File System Hierarchy):** Khác với Windows có ổ C:, D:, Linux bắt đầu mọi thứ từ gốc ```/``` (Root).

- ```/bin```& ```/sbin```: Chứa các lệnh (binary) như ```ls``` ```cp``` ```reboot```   
- ```/etc``` : Chứa các file cấu hình, muốn chỉnh sửa hệ thống thì vào đây
- ```/home``` Chứa dữ liệu người dùng
- ```/var``` Chứa dữ liệu biến đổi như Logs, Database
- ```/tmp``` chứa file tạm, sẽ bị xóa sau khi khởi động lại
- ```/mnt``` và ```/media```: Nơi gắn (mount) ổ đĩa ngoài, USB
**2. Quản lý phần mềm ( Package management)**
- Cập nhật danh sách gói : ``` sudo apt update```
- ```sudo apt install [phần mềm]```
- ...
**3. Quản lý ổ đĩa (Storage)
- ```lsblk```: Liệt kê các ổ đĩa và phân vùng
- ```df -h```: Xem dung lượng trống của các ổ đĩa (Dễ đọc).
  
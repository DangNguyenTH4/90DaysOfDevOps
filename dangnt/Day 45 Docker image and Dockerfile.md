**1. Dockerfile:** Là một file văn bản (không có đuôi) chứa các lệnh để "xây" (build) ra Image. Các lệnh quan trọng:
- ```FROM```    : Chọn Image gốc (Base Image). Ví dụ: ```FROM ubuntu:20.04```     
- ```RUN```    : Chạy lệnh Linux trong lúc build. Ví dụ: ```RUN apt-get install python3```
- ```COPY```    : Copy file từ máy tính vào Image. Ví dụ: ```COPY . /app```
- ```CMD```: Lệnh sẽ chạy khi Container khởi động. Ví dụ: ```CMD ["python3", "app.py"]```
**2. Quy trình Build:**  ```docker build -t ten-image-cua-ban .```

- ```-t``` : Đặt tên (tag) cho image.
- ```.```    : Tìm Dockerfile ở thư mục hiện tại.

**3. Layers (Các lớp):** Mỗi dòng lệnh trong Dockerfile sẽ tạo ra một "lớp" (layer) mới đè lên nhau. Docker rất thông minh, nếu bạn không sửa dòng đó, nó sẽ dùng lại lớp cũ (cache) để build siêu nhanh.

**Câu hỏi:** Trong Dockerfile, lệnh ```RUN```  và lệnh ```CMD```  khác nhau chỗ nào? 
A. ```RUN``` chạy lúc build image (cài cắm phần mềm), còn ```CMD``` chạy lúc khởi động container (chạy ứng dụng). 
B. ```RUN``` chạy trên Linux, ```CMD```
 chạy trên Windows. 
 C. Hai lệnh này giống hệt nhau, dùng cái nào cũng được.
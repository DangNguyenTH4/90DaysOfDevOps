Hôm nay chúng ta đi sâu vào 2 khái niệm quan trọng nhất để chạy ứng dụng.

**1. Pod:**

- Như đã nói, là đơn vị nhỏ nhất.
- Nhưng Pod rất "mong manh dễ vỡ". Nếu Pod chết, nó chết luôn. K8s không tự dựng lại nó trừ khi có người quản lý nó.

**2. Deployment:**

- Là "người quản lý" của Pod.
- Bạn khai báo với Deployment: "Tôi muốn có 3 bản sao (replicas) của Pod Nginx".
- Deployment sẽ tạo ra 3 Pod. Nếu 1 Pod chết, Deployment thấy chỉ còn 2, nó sẽ tạo thêm 1 cái mới ngay lập tức để đảm bảo luôn đủ 3.
- **Tính năng Self-healing (Tự phục hồi)**: Đây là sức mạnh thực sự của K8s.

**Câu hỏi:** Bạn đang có một Deployment tên là ```my-web``` đang chạy 3 Pods. Bạn muốn nâng cấp ứng dụng lên phiên bản mới (Image mới). Bạn chạy lệnh cập nhật image cho Deployment. K8s sẽ làm gì? 
A. Tắt bụp cả 3 Pod cũ cùng lúc, rồi bật 3 Pod mới lên (Downtime một chút). 
B. Tắt từng Pod cũ và bật từng Pod mới thay thế dần dần (Rolling Update - Không Downtime). 
C. Giữ nguyên 3 Pod cũ, bật thêm 3 Pod mới chạy song song mãi mãi.
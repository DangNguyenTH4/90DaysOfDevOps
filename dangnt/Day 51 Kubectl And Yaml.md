**1. Kubectl (Kube Control):**

- Đây là công cụ dòng lệnh (CLI) để điều khiển K8s Cluster.
- **Các lệnh cơ bản:**
    - ```kubectl get nodes```: Xem danh sách máy trong cụm.
    - ```kubectl get pods``` : Xem danh sách Pod đang chạy.
    - ```kubectl run nginx --image=nginx```: Chạy nhanh một Pod nginx.
    - ```kubectl delete pod <tên-pod>```: Xóa Pod.

**2. YAML (Yet Another Markup Language):**

- Trong thực tế, chúng ta ít dùng lệnh  ```kubectl run```mà sẽ viết cấu hình vào file YAML (giống ```docker-compose.yml```) rồi đưa cho K8s.
- Tại sao? Vì file YAML lưu lại được ("Infrastructure as Code"), dễ quản lý phiên bản, dễ review.
- Lệnh áp dụng file YAML: ```kubectl apply -f <tên-file.yaml>```.

**Câu hỏi:** Bạn muốn xem chi tiết lỗi của một Pod đang bị trạng thái "CrashLoopBackOff" (khởi động lên rồi chết ngay lập tức). Lệnh nào sau đây giúp bạn xem **log** của Pod đó? 
A. ```kubectl get pod <tên-pod>```
B. ```kubectl describe pod <tên-pod>```
C. ```kubectl logs <tên-pod>```

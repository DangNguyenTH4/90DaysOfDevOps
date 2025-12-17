Docker rất tuyệt, nhưng khi bạn có hàng trăm container chạy trên hàng chục máy chủ, làm sao để quản lý?

- Container nào đang chạy ở đâu?
- Nếu một container chết, ai sẽ bật lại nó?
- Nếu server A hỏng, làm sao chuyển hết container sang server B?

Đó là lúc cần đến **Container Orchestration** (Điều phối Container), và **Kubernetes** là ông vua trong lĩnh vực này.

**Các khái niệm cốt lõi:**
1. **Cluster**: Một cụm gồm nhiều máy tính (Nodes) nối với nhau để chạy K8s.
2. **Node**: Một máy tính (ảo hoặc thật) trong cụm.
    - **Control Plane (Master)**: Bộ não điều khiển, ra lệnh.
    - **Worker Node**: Công nhân, nơi thực sự chạy các container.
3. **Pod**: Đơn vị nhỏ nhất trong K8s. Một Pod chứa 1 hoặc nhiều Container. K8s quản lý Pod, không quản lý trực tiếp Container.
4. **Deployment**: Quản lý các bản sao (Replicas) của Pod. Ví dụ: "Tôi muốn luôn có 3 Pod Web App chạy". Nếu 1 cái chết, Deployment sẽ đẻ ra cái mới bù vào.
5. **Service**: Cung cấp một địa chỉ IP cố định để truy cập vào các Pod (vì Pod chết đi sống lại liên tục, IP đổi liên tục).

**Câu hỏi:** Trong Kubernetes, đơn vị nhỏ nhất mà bạn có thể tạo và quản lý là gì? 
A. Container B. Pod C. Node
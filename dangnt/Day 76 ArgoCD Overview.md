Gitops và ArgoCD
**1. GitOps là gì?**
- Là phương pháp sử dụng Git làm "nguồn chân lý" (Single Source of Truth) cho toàn bộ hạ tầng và ứng dụng.
- Thay vì chạy lệnh ``` kubectl apply -f deployment.yaml``` thủ công, ta commit file ```deployment.yaml``` lên Git. Một công cụ như (ArgoCD ) sẽ tự động đồng bộ (sync) thay đổi đó vào Kubernetes cluster.
**2.ArgoCD**
- Là công cụ **Continuous Delivery** dành riêng cho Kubernetes, hoạt động theo mô hình GitOps.
- ArgoCD liên tục theo dõi Git Repository. NẾu thấy sự khác biệt giữa Git (Desired State) và Kubernetes (Current State), nó sẽ tự động đồng bộ để Kubernetes giống hệt Git.
- Có giao diện trức quan cực đẹp để xem trạng thái các ứng dụng trong Cluster.

Câu hỏi: Trong mô hình GitOps với ArgoCD, Nếu ai đó lỡ tay xóa mật một Deployment quan trọng trên Kubernetes bằng lệnh ```kubectl delete```, điều gì sẽ xảy ra tiếp theo (Giả sử ArgoCD đang bật chế độ Auto-Sync)?
A. Deployment đó sẽ mất vĩnh viễn.
B.ArgoCD sẽ phát hiện sự khác biệt (OutOfSync) và tự động tạo lại Deployment ddos dự trên cấu hình đang lưu trong Git.
C.ArgoCD sẽ tự động xóa luôn file cấu hình trong Git để đồng bộ với Cluster.

B, ArgoCd sẽ phát hiện cso 2 cơ chế để phát hiện là argocd sẽ poll theo thời gian mặc định là 3 phút. 2 là dùng webhook.
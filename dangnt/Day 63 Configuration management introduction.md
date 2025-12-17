**1. Configuration management (CM) là gì?**
- Nếu IaC (TF) giúp bạn xây nhà ( tạo Server, Network), thì CM (Ansible, Chef, Puppet) giúp bạn trang trí nội thất (cài phần mêm, sửa file config, tạo user...)
- IaC tập trung vào Provisioning (cấp phát)
- CM tập trung vào Configuration (Cấu hình) và duy trì trạng thái mong muons (Desired state)
**2. Tại sao chọn Ansibles**
Trong các công cụ CM(Chef, puppet, saltstack, ansible) chúng tasex học Ansible vì:
- **Agentless:** Không cần cài gì lên server đích cả, chỉ cần SSH là đủ. (Chef/Puppet cần cài Agent).
- **Dễ học:** dùng YAML (lại là YAML!) để viết kịch bản (Playbook).
- **Phổ biến:** Cộng đồng cực lớn.

Câu hỏi: Điểm khác biệt lớn nhất về kiến trúc (Architecture) giữa Ansible so với Chef/puppet là gì?
A. Ansible chạy trên windows, còn chef/puppet chỉ chạy trên linux
B. Ansible là **Agentless** ( khong cần cài phần mềm lên máy đihcs), còn Chef/Puppet thường yêu cầu cài Agent.
C. Ansible viết bằng Java, còn Chef/Puppet viết bằng python.


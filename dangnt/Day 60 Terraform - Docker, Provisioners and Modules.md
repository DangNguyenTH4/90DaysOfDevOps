**Terraform với Docker** : Không chỉ tạo máy ảo. Tf còn có thể điều khiển Docker để tạo Container. Ví dụ:
```hcl
resource "docker_container" "nginx" {
	image = "nginx:latest"
	name = "tutorial"
	ports {
		internal = 80
		external = 8000
	}
}
```
điều này cho thấy TF rất linh hoạt, quản lý được nhiều loại tài nguyên khác nhau.
**Provisioners**
- Đôi khi TF tạo xong server(resource) nhưng bạn muốn chạy thêm mtj vài lệnh Linux bên trong server đó (ví dụ: apt-get update, cài Docker...)
- Provisioner giúp bạn làm điều này.
	- ```local-exec```: Chayjh lệnh trên máy tính của bạn (nơi chạy TF )
	- ```remote-exec```: SSH vào server vừa tạo và chạy lệnh trên đó.
	- *Lưu ý*: HashiCorp khuyên hạn chế dùng Provisioner, nên dùng các công cụ chuyên dụng như Ansible Hoặc User Data của Cloud thì tốt hơn.

**Modules:**
- Module giống như "thư viện" hoặc "hàm" trong lập trình.
- Bạn jđóng gói một nhóm tài nguyên (ví dụ: 1VPC + 2 subnet + 1 gateway) thành 1 module.
- Sau này muốn tạo mạng, chỉ cần gọi Module đó ra dùng lại, không cần viết lại từ đầu.

Câu hỏi: Lợi ích chính của việc sử dụng **TF Modules** là gì?
A. Giúp code chạy nhanh hơn.
B. Giúp tái sử dụng cod (Resusability), tổ chức cod gọn gàng và chia sẻ kiến trúc chuẩn cho team.
C. Giúp Terraform kết nối được với Docker.

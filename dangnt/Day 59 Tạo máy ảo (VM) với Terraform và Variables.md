**Khai báo Resource**
```hcl
resource "virtualbox_vm" "node" {
	count = 2 # tạo 2 máy ảo cùng lúc
	name = format("node-%02d", count.index + 1) # tên node: node-01, node-02
	image = "ubuntu-bionic"
	cpus = 2
	memory = "512 mib"
}
```
Chỉ cần sửa ``` count = 3 ``` và chạy ``` terraform apply ```, Terraform sẽ tự động tạo thêm 1 máy nữa. Đó là sức mạnh của IaC.
**Variables"**
Thay vì fix cứng các giá trị (hard-code) như "512 mib", hay tên image, t a nên dùng biến để tái sử dụng code dễ hơn.
- Khai báo biến trong file ```variables.tf```.
- Gán giá trịn trong file ```terraform.tfvars```.
- Dùng biến trong code: ```var.memory``` , ```var.cpu_count``` 

Câu hỏi: Trong terraform, nếu bạn muốn tạo nhiều tài nguyên giống hệ nhau (ví dụ: 5 máy ảo cho web server) mà không phải copy-paste đoạn code ```resource``` 5 lần, bạn nên sử dụng thuộc tính nào?
A. ```loop```
B. ```repeat```
C. ```count``` hoặc ```for_each``` 

**HCL**
- Là ngôn ngữ cấu hình riêng của HashiCorp
- Được thiết kế để vừa dễ đọc cho người vừa dễ phân tích cho máy (machine-friendly)
- Nó nằm giữa JSON và YAML
**Cấu trúc cơ bản của một file** .tf

```hcl
# 1. Provider: Khai báo bạn muốn làm việc với ai (AWS, Azure, Google...)
provider "aws" {
  region = "us-west-1"
}

# 2. Resource: Khai báo bạn muốn tạo cái gì (Server, Database...)
resource "aws_instance" "my_server" {
  ami           = "ami-12345678"
  instance_type = "t2.micro"
  
  tags = {
    Name = "Hello-Terraform"
  }
}
```
**Terraform State** ```(terraform.tfstate)```
- Khi chạy ```terraform apply``` , Terraform sẽ tạo ra một file JSON tên là ```terraform.tfstate```. 
- File này lưu giữ trạng thái thực tế của hạ tầng. Terraform duhgn nó để biết cái gì đã tạo rồi, cái gì chưa, cái gì đã bị thay đổi.
- Quan trọng: File này chưa thông tin nhạy cảm (password, key) cần được bảo bệ kỹ
Ask: Tại jsao chúng ta Không Nên sửa trực tiếp file ```terraform.tfstate``` bằng tay? 
A. Vì nó là file nhị phân (binary), không mmowr được bằng text editor.
B. Vì Terraform sẽ tự động ghi đè lại file này, công sứ sửa sẽ mất
C. Vì file này là "bộ nhớ" của Terraform, sửa tay sẽ làm leechjj lạc thông tin giữa thực tế và code, dẫn đến Teraform hoạt động sai hoặc phá hỏng hạ tầng.

```
  ```
  ```
**1. Cài đặt jenkins**
- Có nhiều cách cài: Cài trực tiếp trên OS (Linux/Window), chạy Docker Container, hoặc deploy lên Kubernetes. (**Kubernetes (Minikube)** bằng Helm Chart)
- Các bước chính
	- 1. Tạo namespace jenkins
	- 2. Tạo PV (persistent Volume (để lưu dữ liệu pipeline không bị mất khi pod restart)
	- 3. Dùng Helm để instal Jenkins
	- 4. Lấy pasword admin và đăng nhập.

**2. Jenkins Pipeline (Jenkinsfile):**
- Đây là khái niệm quan trọng nhất: **Pipeline as code**.
- Thay vì click chuột cấu hình job trên giao diện, ta viết toàn bộ quy trình vào 1 file text là ```Jenkinsfile```
- Cấu trúc cơ bản (Declarative Pipeline):
```groovy
pipeline {
	agent any
	stages {
		stage('Build'){
			steps {
				echo 'Building...'
			}
		}
		stage('Test'){
			steps{
				echo 'Testing...'
			}
		}
		stage('Deploy'){
			steps {
				echo 'Deploying...'
			}
		}
	}
}
```
Câu hỏi:
Trong Jenkins Declarative Pipeline, khối lệnh nào được sử dụng để định nghĩa các giai đoạn chính của quy trình (như build, test, deploy)?
A. ```steps{}```
B. ```stages{}```
C. ```scripts{}```

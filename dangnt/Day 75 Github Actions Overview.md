Một đối thủ đáng gớm khác của Jenkins đó là **Github Actions**
**1. Github Actions là gì?**
- Là nền tảng CI/CD được tích hợp sẵn ngay trong GitHub. Không Cần cài đặt server riêng như Jenkins.
- Cấu hình bằng File Yaml nằm trong thư mục ```.github/workflows/```.
**2. Các thành phần chính:**
- **Workflow:** Quy trình tự động hóa (Ví dụ: Build & Test)
- **Event**: Sự kiện kích hoạt Workflow (Ví dụ: ```push, pull_request```)
- **Job**: Tập hợp các bước (Steps) chạy trên cùng một **Runner**
- **Runner:** Server chạy Job (có thể là Github-hosted runner hoặc Self-hosted runner).
- **Action:** Các task nhỏ được đóng gói sẵn (ví dụ: ```actions/checkout```) để lấy code, ```action/setup-node``` để cài Node.js
**3.Ví dụ Workflow:**
```yaml
name: CI
on: [push]
jobs:
	build:
		runs-on: ubuntu-latest
		steps:
			- uses: actions/checkout@v2
			- name: Run a one-line script
			- run: echo Hello, world! 		
```
Câu hỏi: Trong github actions,để sử dụng một action đã được cộng đồng viết sẵn (Ví dụ: action để login vào Docker Hub), chúng ta sử dụng từ khó nào trong bước step của Job?
A. ```run```
B. ```call```
C. ```uses```

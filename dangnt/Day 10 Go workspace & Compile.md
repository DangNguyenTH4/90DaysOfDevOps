1, Workspace ( Không gian làm việc )
- Go rất ngăn nắp, và thuongwf yêu cầu code nằm trong một thư mục gọi là GOPATH (mặc định là ~/go)
- Trong đó có 3 thư mục con chính:
	- ```src``` : Chứa source code
	- ```pkg``` : Chứa các package đã biên dịch để lần sau build nhanh hơn
	- ```bin``` : Chứa các file chạy ( executable) sau khi cài đặt
2, 3 lệnh biên dịch thần thánh
- ``` go run ``` : Chạy luôn code ( biên dịch tạm vào thư mục temp, chạy xong xóa luôn). Dùng khi đang code/test
- ```go build``` Biên dịch ra file chạy nằm ngay tại thư mục hiện tại.
- ```go install``` Biên dịch và đưa file chạy vào thư mục ```bin``` để có thể gọi lệnh đó từ bất cứ đâu trong terminal
*Thực hành* : Thử chạy lệnh ```go install``` trong thư mục hello. Sau đó gõ lệnh ```ls ~/go/bin``` xem có thấy file gì mới không

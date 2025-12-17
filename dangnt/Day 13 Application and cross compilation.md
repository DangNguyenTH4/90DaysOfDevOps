1, Demo Go twitter, 
2, Cross-Compilation (Biên dịch chéo) - Sức mạnh của Go: Đây là tính năng "ăn tiền" của Go. Từ máy tính của bạn (ví dụ Windows), bạn có thể build ra file chạy cho Linux hoặc MacOS chỉ bằng 1 dòng lệnh!
Cú pháp: ```GOOS=[hệ điều hành] GOARCH=[chip] go build main.go```
ví dụ :
- Build cho Linux: ``` GOOS=linux GOARCH=amd64 go build -o myapp-linux main.go```
- Build cho MAC m1/m2 : ```GOOS=darwin GOARCH=amd64 go build -o myapp-mac main.go```
- Build cho windows : ```GOOS=windows GOARCH=amd64 go build -o myapp.ext main.go```
Bài tập: Hãy thử chạy lênh build ra môt phiên bản cho hệ điều hành khác từ máy.

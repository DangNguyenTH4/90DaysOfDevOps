```go
package main // 1. Khai báo package  
  
import "fmt" // 2. Import thư viện  
  
func main() { // 3. Hàm main - điểm bắt đầu  
fmt.Println("Hello #90DaysOfDevOps") // 4. In ra màn hình  
}
```


**Giải thích nhanh:**

1. ```package main``` : Mọi file Go đều phải thuộc về một package.  ```main``` là package đặc biệt, báo cho Go biết đây là chương trình có thể chạy được (executable), không phải thư viện (library).
2. ```import "fmt"```: ```fmt```(format) là gói chuẩn của Go để nhập/xuất dữ liệu (in ra màn hình).
3. ```func main()```: Đây là cửa chính. Khi chạy chương trình, máy tính sẽ tìm hàm ```main```để chạy đầu tiên.

**Biên dịch (Compile):** Go là ngôn ngữ biên dịch.

- ```go run main.go``` : Biên dịch và chạy luôn (thường dùng khi dev).
- ```go build main.go```: Biên dịch ra file chạy (```.exe```trên Windows hoặc binary trên Linux). File này đem sang máy khác chạy không cần cài Go.

**Câu hỏi nhỏ:** Nếu tôi đổi tên hàm ```func main()``` thành ```func start()```, chương trình có chạy được không? Tại sao?
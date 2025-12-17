**1.CI - Continuous Integration **
- Là việc các Dev thường xuyên merge code vào kho chung (Shared Repository) nhiều lần trong ngày
- Mỗi lần merge sẽ kích hoạt quy trình tự động : Build - > Test ...
- Mục tiêu: Phát hiện lỗi sớm (Fail fast)
**2. CD - Continuous Deployment / Delivery**
- Sau khi CI  thành công (Code sạch, test pass) , CD sẽ tự dộng deploy code đó ra các môi trường (Staging, Production).
- **Continuous Delivery:** Tự động deploy ra staging, nhưng deploy ra Production cần bấm nút xác nhận cảu con người
- **Continuous Deployment** : Tự động hoàn toàn ra production nếu test pass.

Câu hỏi: Lợi ích lớn nhất của việc áp dụng CI/CD Pipeline so với quy trình thủ công truyền thống là gì?
A. Giúp Developer viết code nhanh hơn gấp đôi.
B. Giúp phát hiện lỗi sớm, giảm thiểu rủi ro khi release, và đưa sản phẩm đến tay người dùng nhanh hơn (Time to Market).
C.  Giúp loại bỏ hoàn toàn vai trò của Tester/QA trong team.

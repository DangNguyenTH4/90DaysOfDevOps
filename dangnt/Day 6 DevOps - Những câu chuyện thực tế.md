Hôm nay chúng ta sẽ xem xem các ông lớn đã áp dụng devops như thế nào:
1. Amazon: 
	- Năm 2010, họ chuyển sang AWS cloud
	- Năm 2011, họ đạt được khả năng deploy code trung bình 11.6s/ lần
	- Developer có quyền deploy code bất cứ lúc nào họ muốn
2. Netflix:
	- Dịch vụ streaming khổng lồ với trải nghiệm mượt mà
	- Developer tự build code thành image và deploy mà không cần nhờ team Ops
	- Hệ thống Continiuous Monitoring sẽ tự động rollback nếu phiên bản mới bị lỗi
3. Esty
	- Cho phép developer deploy code từ năm 2009
	- Triết lý: Khi Developer chịu trách nhiệm deploy, họ cũng sẽ có trách nhiệm hơn với hiệu năng và độ ổn định của ứng dụng
=> DevOps không chỉ là công cụ mà là sự trao quyền (empowerment) cho Developer và văn hóa chấp nhận rủi ro có kiểm soát (Fail fast, fix fast)
**Câu hỏi thảo luận:** Bạn nghĩ sao về việc cho phép Developer tự ý deploy code lên Production bất cứ lúc nào? Liệu có quá nguy hiểm không?
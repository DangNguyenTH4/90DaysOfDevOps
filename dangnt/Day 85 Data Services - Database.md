Việc chọn đúng lọa Database là quyết định sống còn cho hiệu năng và khả năng mở rộng của ứng dụng. 
Có các loại chính sau:
1. **Relational (SQL):** Dự liệu có cấu trúc, quan hệ chặt chẽ, Đảm bảo tính **ACID** (mysql PostgresSQL...)
2. **Document (NoSQL):** Lưu dữ liệu dưới dạng JSON/BSON. Linh hoạt, dễ mở rộng, Ví dụ: MongoDB.
3. **Key-Value:** Siêu nhanh, lưu cạp khóa - giá trị. Thường dùng để làm Cache. Ví dụ: Redis.
4. **Wide Column:** Lưu dữ liệu theo cột phù hợp cho dữ liệu khổng lồ, ghi nhiều đọc ít. Ví dụ : Cassandra.
5. **Graph:** Lưu các mối quan hệ phức tạp giữ các thực thể. Ví dụ Neo4j.
6. **Search Engine:** Chuyên dụng cho tìm kiếm văn bản. Ví dụ: **Elasticsearch.
7. **Time series Database(TSDB)** : 
8. **Vector Database**
Câu hỏi: Nếu bạn đang xây dựng một hệ thống **Ngân hàng** để chuyển tiền giữa các tài khoản, tính chất nào của Database là quan trọng nhất để đảm bảo rằng nếu giao dịch đang diễn ra mà bị mất didenj thì tiền không bị "Bốc hơi" hoặc bị nhân đôi?
A. Khả năng mở rộng ngang(Horizontal Scaling).
B. Tính ACID (Đặc biệt là Atomicity và Consistency).
C. Tốc độ truy vấn (Query Speed).

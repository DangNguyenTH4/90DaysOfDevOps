Hôm qua chúng ta đã chạy từng container lẻ tẻ. Nhưng thực tế, một ứng dụng thường gồm nhiều phần: Web App + Database + Cache... Chạy từng lệnh ```docker run``` cho mỗi cái thì rất mệt và dễ sai sót.

**1. Docker Compose là gì?**

- Là công cụ giúp bạn định nghĩa và chạy **nhiều container** cùng lúc.
- Bạn viết cấu hình vào một file tên là ```docker-compose.yml```(định dạng YAML).
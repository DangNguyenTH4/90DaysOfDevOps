Hôm nay chúng ta nói về nơi lưu trữ dữ liệu trên Azure.

**1. Azure Storage Account:** Là cái kho chứa đủ thứ:

- **Blob Storage**: Chứa file (ảnh, video, log). Giống Google Drive/S3.
- **File Storage**: Giống File Server truyền thống (SMB), có thể mount vào máy tính như ổ đĩa mạng.
- **Redundancy (Sao lưu dự phòng)**:
    - **LRS (Locally-redundant)**: Copy 3 bản trong cùng 1 tòa nhà (Rẻ nhất).
    - **GRS (Geo-redundant)**: Copy sang Region khác (Ví dụ: Dữ liệu chính ở Singapore, bản backup tự động ở Hong Kong). Chống thảm họa động đất/sóng thần.

**2. Database Models:**

- **Azure SQL Database**: SQL Server phiên bản PaaS. Không cần cài đặt, tự động vá lỗi, tự động backup.
- **Azure Cosmos DB**: NoSQL Database siêu mạnh, phân tán toàn cầu. Dùng cho các ứng dụng cần độ trễ cực thấp (Game, Real-time App).
- **Azure Cache for Redis**: Bộ nhớ đệm (Cache) giúp web chạy nhanh hơn.

**Câu hỏi:** Công ty bạn yêu cầu lưu trữ dữ liệu khách hàng cực kỳ quan trọng, không được phép mất dù cả đất nước chứa Data Center đó bị chìm xuống biển. Bạn nên chọn loại Redundancy nào cho Storage Account? A. LRS (Locally-redundant storage) B. ZRS (Zone-redundant storage) C. GRS (Geo-redundant storage)
Hôm nay tác giả hướng dẫn dựng một phòng Lab mạng xịn sò để thực hành Automation.

**Công cụ: EVE-NG**

- Đây là phần mềm giả lập mạng chuyên nghiệp (Network Emulator).
- Khác với Packet Tracer (chỉ là mô phỏng phần mềm), EVE-NG chạy các image hệ điều hành thật của Cisco, Juniper, Mikrotik... nên lệnh và hành vi giống thật 100%.
- **Mô hình Lab:**
    - 1 Router (Gateway ra Internet).
    - 4 Switch (Kết nối các máy con).
    - Mục tiêu: Dùng Python để cấu hình tự động cho 5 thiết bị này.

_Lưu ý: EVE-NG khá nặng và cài đặt phức tạp (cần máy ảo, CPU hỗ trợ ảo hóa lồng nhau - Nested Virtualization). Nếu máy bạn không đủ mạnh, chúng ta có thể chỉ cần nắm concept là được._

**Câu hỏi tư duy:** Tại sao khi làm Automation, chúng ta nên test trên môi trường Lab (như EVE-NG) trước khi chạy trên hệ thống thật (Production)? (Nghe có vẻ hiển nhiên, nhưng hãy thử kể ra 1 rủi ro lớn nhất nếu chạy thẳng script lên Production).

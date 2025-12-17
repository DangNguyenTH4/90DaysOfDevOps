Chính xác! DHCP là thủ phạm.

Hôm nay chúng ta nói về xu hướng mới: **Network Automation**. Thay vì ngồi gõ lệnh cấu hình từng con Router/Switch bằng tay (dễ sai sót, tốn thời gian), chúng ta dùng Code để làm việc đó.

**Tại sao cần Automation?**

- **Tốc độ**: Cấu hình 100 con Switch trong 5 phút thay vì 5 ngày.
- **Chính xác**: Code chạy thì không bao giờ gõ sai chính tả như người.
- **Lưu vết**: Code được lưu trên Git, ai sửa gì biết ngay.

**Công cụ phổ biến:**

1. **Ansible**: Rất mạnh, không cần cài agent lên thiết bị mạng. Dùng YAML dễ đọc.
2. **Python**: Ngôn ngữ lập trình quốc dân cho Network Engineer (thư viện Netmiko, Nornir).
3. **Terraform**: Dùng để dựng hạ tầng mạng trên Cloud (AWS VPC, Azure VNet).

**Câu hỏi:** Theo bạn, nếu muốn cấu hình tự động cho 50 con Router của Cisco mà không muốn cài thêm phần mềm gì lên Router đó, thì công cụ nào trong số trên là phù hợp nhất?


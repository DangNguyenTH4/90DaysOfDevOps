Hôm nay chúng ta sẽ đi sâu vào việc dùng Python để tự động hóa mạng. Tại sao lại là Python?

- Dễ học, dễ đọc (như tiếng Anh).
- Thư viện phong phú (Netmiko, Paramiko, Napalm...).

**Môi trường thực hành (Lab):** Để học cái này mà không có thiết bị thật (Router Cisco/Juniper đắt tiền), chúng ta dùng giả lập.

- **EVE-NG**: Công cụ giả lập mạng cực mạnh (nhưng cài đặt hơi chua, cần máy mạnh).
- **GNS3**: Tương tự EVE-NG.

**Code Python "Hello World" cho Network:** Thay vì ```print("Hello World")``` , chúng ta sẽ viết script để SSH vào Router và lấy thông tin. Ví dụ dùng thư viện ```netmiko```:
```python
from netmiko import ConnectHandler

cisco_router = {
    'device_type': 'cisco_ios',
    'host':   '192.168.1.10',
    'username': 'admin',
    'password': 'password',
}

net_connect = ConnectHandler(**cisco_router)
output = net_connect.send_command('show ip int brief')
print(output)
```

Đoạn code trên sẽ tự động đăng nhập vào Router và chạy lệnh ```show ip int brief``` để xem trạng thái các cổng mạng.
**Câu hỏi:** Trong đoạn code trên, nếu bạn muốn chạy lệnh để xem bảng định tuyến (routing table) thay vì xem cổng mạng, bạn sẽ sửa dòng ```send_command``` thành gì? (Gợi ý: Lệnh xem route trên Cisco là ```show ip route``` ).
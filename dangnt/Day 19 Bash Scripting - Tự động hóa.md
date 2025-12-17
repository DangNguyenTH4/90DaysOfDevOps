**Script đầu tiên**
```bash
#!/bin/bash
echo "Xin chào, tôi là script!"
mkdir test_folder
cd test_folder
touch file_trong_folder.txt
echo "Đã tạo xong folder và file."
```
**Biến và điều kiện**
```bash
#!/bin/bash
name="Dang"
echo "Hello $name"

if [ "$name" == "Dang" ]; then
    echo "Bạn là admin!"
else
    echo "Bạn là khách."
fi
```
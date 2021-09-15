- Mở `terminate` (trên Linux, macOS hoặc `cmd` trên Windows) rồi gõ dòng lệnh:

````cmd
ssh-keygen -t rsa
````

- Hỏi nhập thư mục sẽ lưu key sinh ra, hãy nhập thư mục - tên file muốn lưu
- Hỏi nhập password để connect vào ssh privited key
- Sau khi hoàn tất sẽ sinh ra 2 file `Private Key` và `Public Key`
- Dùng lệnh `clip < ~/.ssh/id_rsa.pub` để copy nội dụng của file `.pub`
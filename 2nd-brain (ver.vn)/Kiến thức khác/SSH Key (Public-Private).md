# Generate SSH Key (Public-Private)

- Mở `terminate` (trên Linux, macOS hoặc `cmd` trên Windows) rồi gõ dòng lệnh:

````cmd
ssh-keygen -t rsa
````

- Hỏi nhập thư mục sẽ lưu key sinh ra, hãy nhập thư mục - tên file muốn lưu
- Hỏi nhập password để connect vào ssh privited key
- Sau khi hoàn tất sẽ sinh ra 2 file `Private Key` và `Public Key`
- Dùng lệnh `clip < ~/.ssh/id_rsa.pub` để copy nội dụng của file `.pub`

# How to manage passphrase of an SSH key

### Steps to change passphrase of SSH key

1.  Run _ssh-keygen_ with _-p_ option .
    
    $ ssh-keygen -p 
    
2.  Specify the location of your _SSH_ private key.
    
    Enter file in which the key is (/home/user/.ssh/id_rsa):
    
    Default location is selected by default
    
3.  Enter existing passphrase for the private key.
    
    Enter old passphrase:
    
4.  Comment of the private key will be displayed.
    
    Key has comment 'user@host'
    
5.  Enter a new passphrase for the key twice.
    
    Enter new passphrase (empty for no passphrase):
    Enter same passphrase again:
    
6.  Confirmation message will be displayed.
    
    Your identification has been saved with the new passphrase.
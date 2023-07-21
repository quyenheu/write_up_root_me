- tiêu đề : File upload - ZIP : chỗ cho ae upload file zip 
- nội dung : đọc được index.php 

- NOTE : uhm bài này anh em phải có kiến thức về hệ điều hành và symlink , nếu không cũng khó cho mình giải thích :v ( sr nếu ae k hiểu )
- trước tiên mình giải thích qua về symlink : mấy cái icon ngoài màn hình desktop thật chất nó là một biểu tượng thôi và được kết nối đến nguồn lưu ở chỗ khác và trên linux họ gọi là symlink 
- vậy sẽ ra sao nếu ae trỏ 1 con symlink đến index.php trên máy mình rồi up lên server -> có phải nó sẽ trỏ đến index.php nhưng trên server không 
- tiếc là brower chặn việc truyền symlink qua mạng --> đúng bài òi zippppp

- ae nên tìm hiểu thêm nhé mình không giỏi vụ giải thích lắm 

- xem qua web và up thử zip lên 

![Alt text](<../image/18.1.png>)

- sau đó truy cập để xem file zip mình vừa up lên ( web này tự unzip ra bằng hàm ZipArchive() này ae thử up lỗi là ra)

![Alt text](<../image/18.2.png>)

- thì mình up thằng luôn symlink link đến index.php ( cái link_to_index ) , ấn vào xem 

![Alt text](<../image/18.3.png>)

- okay flag ở trên nếu quá cayy ae có thể get 

- mình cũng up luôn file zip cho ae nghiên cứu này

![Alt text](<../image/oka.zip>) nếu lỗi form ae qua image tìm oka.zip nhé 

#hackerone2101:
- ae nên tìm hiểu về symlink nhé , tự học là kỹ năng cần có của hacker lỏ mà :> 
- nếu cần giải đáp cứ liên hệ với mình qua ig ( README.md ) ưu tiên nữ nhe :> 

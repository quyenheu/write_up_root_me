- tiêu đề : backup file = File backup là một bản sao lưu của dữ liệu hoặc tập tin gốc, mục đích bảo vệ tính an toàn dữ liệu khi xảy ra sự cố
- nội dung : no clue 

- NOTE : vì đây là ctf nên mình sẽ target tiêu đề mà không khai thác lan man nhé :>
- vào view thử hiện ra 1 web login - đây chính là trang index.php 

![Alt text](<../image/12.1.png>)

- mình có tìm hiểu được dấu "~" trong nhiều trường hợp được sử dụng để tạo một bản sao lưu tập tin gốc ( không phải quy ước chuẩn )
- nên mình thử thêm vào URL 

![Alt text](<../image/12.2.png>)

- kết quả là tải được về một file index.php 
- mở nó lên đọc thử 

![Alt text](<../image/12.3.png>)

- NOTE : ae để ý thằng rễ-tôi này thường lấy mật khẩu làm flag ( không có format chung giống như các web ctf khác ) 

#hackerga2101: 
- dev cũng như chúng ta đôi khi chủ quan làm ra những quy ước không an toàn :v 
- nên học thêm các quy ước đời thật đôi lúc sẽ cho ae kết quả bất ngờ 
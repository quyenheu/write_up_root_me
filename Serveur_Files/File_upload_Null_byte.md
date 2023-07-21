- tiêu đề : File upload - Null byte = ae đọc về null byte trước khi làm nhé 
- nội dung : mục tiêu là thực thi được code php 

- view web thấy có một vài thư mục , mà mình target vào upload thoii

![Alt text](<../image/16.1.png>)

- mình up thử 1 file ảnh với nội dung phpinfo()
- NOTE : cách tạo và hướng dẫn chi tiết ae đọc bài file_upload_Double_extensions nhé lười copy zl :<

- up xong ae load lại sẽ thấy được ảnh mình vừa up 

![Alt text](<../image/16.2.png>)

- burpsuite mode on nào 
- như tiêu đề bài này chúng ta sẽ dùng null byte để pypass filter : ok.php%00.jpg 

![Alt text](<../image/16.3.png>)

- ae truy cập vào file php mình vừa tải lên thành công 

![Alt text](<../image/16.4.png>)

- zay là có flag roi

#hackerga2101:
- lỗi xảy ra do server không kiểm tra kỹ và chấp nhận ký tự NULL tạo lỗ hổng này 
- tiêu đề : SQL injection - String 
- nội dung : lấy password của admin

- okay anh em view và dùng thử đã nhé đừng hầm hố . ' vội hehe 

- mình thấy 2 trang login và search là dễ khai thác SQL nhất nên thử trước 

![Alt text](<../image/29.1.png>)

- trang login này mình thử một lúc thì không thấy bị SQLi nên chuyển qua search 
- test thử đã 

![Alt text](<../image/29.3.png>)

- uhm giờ thêm dấu ' xem sao 

![Alt text](<../image/29.4.png>)

- yep syntax error
- lúc này mình thử union base xem sao : -1' union select password from users where username='admin' --a 
- NOTE : đoạn này mình phải khai thác thêm để biết table_name , column_name nhé 

![Alt text](<../image/29.5.png>)

- có vẻ khác số cột rồi thêm 1 vào để dò số cột 

![Alt text](<../image/29.6.png>)

- pem , lụm cờ lụm cờ 

#hackerga2101:
- series này mình không dạy lý thuyết nên cái bước NOTE kia ae tìm hiểu về bảng information_schema nhé 
- quy chuẩn mới của mysql theo mình biết là phải -- + 1 ký tự bất kỳ không như ngày xưa chỉ cần -- thôi 
- ae nào thiện chí thích dùng tool pem hay kiến thức SQL thì contact qua ig mình nhé ( README.md ) hoặc mình up web cho nhé . thanks :>  
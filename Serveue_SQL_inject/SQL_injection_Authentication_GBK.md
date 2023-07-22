- tiêu đề : SQL injection - Authentication - GBK
- nội dung : biết tiếng trung của không , lấy password admin 

- NOTE : ae tìm hiểu về GBK encoding trước nhé , một cách bypass khá dị :v 
- NOTE : bài này ae chịu khó research là ra ( đừng có search write-up như mấy ông đang đọc dòng này nhé :>> ) 

- test thử đã , web có 2 chức năng là login và cho xem tài khoản 

![Alt text](<../image/30.1.png>)

![Alt text](<../image/30.2.png>)

- mình cũng xem xét qua rồi chỉ có cách đấm thằng login thoi 

- mình search rồi nên đưa ae luôn : 
- username=admin%81'+or+1=1+--+-&password=1
- ae muốn hiểu thì tra cái bảng GBK encode nhé 

![Alt text](<../image/30.3.png>)

- uhm không ra gì , nhưng nếu ae để ý kĩ thì nó đang location : logged.php
- ae sửa lại GET vào cái logged.php 

![Alt text](<../image/30.4.png>)

- pem lụm cờ 

#hackerga2101: 
- vì mấy ông tàu , Nhật với Hàn chữ oằn quá nên phải có chuẩn chung -> mấy hacker iq cao lợi dụng vào pem ra SQLi loại này 
- ae nào thiện chí thích dùng tool pem hay kiến thức SQL thì contact qua ig mình nhé ( README.md ) hoặc mình up web cho nhé . thanks :>  

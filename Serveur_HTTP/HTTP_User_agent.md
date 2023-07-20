- tiêu đề : HTTP - User-agent = này là trường user-agent khongg dịch :>
- nội dung : Admin is really dumb... web nói này thì chịu 

- dùng thử nào 
- vào chỉ hiện một nội dung : Wrong user-agent: you are not the "admin" browser! ( sai thì sửa cho đúng thoii )

- thì mình cũng check qua xem source , cookie , .. có gì không 

![Alt text](<../image/4.1.png>)

- cũng không có gì cả 
- burpsuite mode on xem gói tin http 

![Alt text](<../image/4.2.png>)

- họ nói là user-agent sai nên mình thử sửa trường này 

![Alt text](<../image/4.3.png>)

- okay Admin is really dumb...

#hackerga2101:
- tìm hiểu khái niệm cơ bản nhất là source và sink , mình thì gọi là untrusted data với unsafe method 
- ngoài User-agent ra thì trong gói tin http còn nhiều trường nguy hiểm khác như : Cookie , path , parameter ... (hacker có thể gán data vào :v)


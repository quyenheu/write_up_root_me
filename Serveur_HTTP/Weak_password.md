- tên Weak password nhưng cũng thuộc chương HTTP nha

- tiêu đề : Weak password = mật khẩu yếu 
- nôi dung : Nothing too difficult = không gì là quá root-me :v

- lúc vào sẽ có 1 form login ( cái này là basic auth login - đại khái nó sẽ gửi thông tin login qua http request với trường Authorization )

![Alt text](<../image/5.1.png>)

- và như mình nói khi bạn xem request sẽ thấy trường Authorization: basic YWRtaW46MQ== ( encode base64 dịch ra là admin:1 )

![Alt text](<../image/5.2.png>)

- thì như tiêu đề weak password => time to brute force
- Fun Fact : mình login thử lần đầu tiên đúng luôn :> không cần bf  

- Lúc này ae dùng tính năng intruder của burp luôn đỡ phải code ( chuột phải vào bên request -> sent to intruder )

![Alt text](<../image/5.3.png>)

- NOTE : mình hướng dẫn cả những ae không quen dùng burp nên hơi chậm nha
- ấn clear bên ở bên phải -> bôi đen chỗ bash64 mà mình cần brute force vào -> ấn add
- chuyển qua tab payload 
- để brute force thì ae phải có wordlist ( lên mạng search basic wordlist admin tải về )
- giờ code tí để đúng format kia nhé : 

![Alt text](<../image/5.4.png>)

- mình dùng python code thêm admin: trước mỗi password và encode base64
- xong , anh em ấn load ở payload option rồi chọn file password vừa sửa  
- tiếp đến kéo xuống bỏ cái tích ở payload encoding 

![Alt text](<../image/5.5.png>)

- start attack màu cam kiaa nhé 

![Alt text](<../image/5.6.png>)

- ấn cột length để sắp xếp độ dài response thấy cái khác biệt nhất 516 
- pem , win 

#hackerga2101:
- trong thực tế vấn đề weak password khá phổ biến do lỗi chủ quan của người set up 
- tool không phế tôi phế , nên hãy học tool :v 

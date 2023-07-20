- challenge này sẽ là khởi đầu của series liên quan đến HTTP header 

- tiêu đề : IP restriction bypass = bỏ qua giới hạn ip :v ( 10. ielts )
- nội dung : đại khái họ sẽ check ip của user xem có thuộc internal company network không => có thì khỏi cần login luôn (và đây cũng là mục đích của chúng ta)

- let's go , cùng dùng qua nào 

![Alt text](<../image/2.1.png>)

- uhmm vì đây là lab ctf + có nội dung của lab rồi nên mình cũng bỏ qua check vul khác :v 

- mình tự hỏi : chúng ta đang tương tác qua gói tin http với web . vậy có cách nào để thao túng được IP của mình qua http request không ? 
- sau một hồi research mình tìm được header "X-Forwarded-For" ( nôm na : Tiêu đề này chứa địa chỉ IP của user mà đã gửi yêu cầu đến máy chủ proxy hoặc load balancer )

- thử test : mình thêm 1 trường X-Forwarded-For: abc 

![Alt text](<../image/2.2.png>)

- perfect IP của mình đã được đổi thành abc 

- nhưng lại xảy ra một vấn đề là chúng ta không biết dải mạng nội bộ của công ty đó (mẹo khi học mạng máy tính toàn để kiểu 192.168.0.1 :v )
- cách giải đúng là quay lại trang root-me xem có thêm thông tin gì không 
- thì anh em lúc bí có thể xem thử mấy cái related ressource 

![Alt text](<../image/2.3.png>)

- yep ! trong này có thông tin về dải mạng đó 

![Alt text](<../image/2.4.png>)

- ae lấy 1 IP trong 3 dải kia quất thử vào là win 

![Alt text](<../image/2.5.png>)

#hackerga2101: 
- với mình trong thực tế để check xem có misconfig mấy cái header không thì mình thường quét qua với Rustscan 
- mấy ông header này lợi hại lắm nên ae tìm hiểu thêm nhee 
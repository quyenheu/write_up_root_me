- tiêu đề : File upload - MIME type 
- nội dung : ae cần RCE được server và đọc flag ở /.passwd

-  NOTE : theo mình bài này hơi sai tiêu đề chút :v 

- trước tiên vào web trông đen đen như tương lai tán crush z 

- mình qua thư mục upload và up thử một file ảnh với nội dung phpinfo()
- NOTE : cách tạo và hướng dẫn chi tiết ae đọc bài file_upload_Double_extensions nhé lười copy zl :<

![Alt text](<../image/15.1.png>)

- để xem ảnh ae up lên thì load lại thư mục upload là có nhé 

![Alt text](<../image/15.2.png>)

- burpsuite mode nào 
- vì đề bài là MIME type nên mình thêm GIF89a ; vào đầu nội dung ( ae tìm hiểu MIME type nhé 1 cách bypass khá hay )
- và sửa đuôi file thành php 

![Alt text](<../image/15.3.png>)

- thử check xem thực thi được code chưa , load lại upload và chọn vào ok.php

![Alt text](<../image/15.4.png>)

- pem , win 
- phần khai thác flag mình có làm chi tiết ae đọc bài file_upload_Double_extensions nhé 

- giải thích chút NOTE1 : 
+ nhưng mình chợt nhận ra quên cho GIF89a ; vào nhưng vẫn lưu được ok.php ( ủa vậy MIME type gì ở đây ) 
+ mình thử đổi content-type thì lúc này đúng là không up được -> tiêu đề nên để là content type mới đúng ( hoặc là rễ-tôi đang fake ae mình :> )

#hackerga2101: 
- MIME-type và content-type là hai trường rất hay trong challenges file upload 
- nào mình dựng lại lab cho ae nghịch nhé :>> maybe domain là hackerga.lo 

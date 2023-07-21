- tiêu đề : PHP - Command injection 
- nội dung : tìm lỗ hổng và exploit nó 

- nguyên căn của lỗi cmdi là do untrusted data (source) rơi vào hàm thực thi câu lệnh hệ thống (sink) như system() , eval() , passthru()
- mới vào ae có khung ping , thì mình nhập 1.1.1.1 để ping thử xem sao 

![Alt text](<../image/22.1.png>)

- bản chất loại lỗi injection là việc ae có thể nối dài câu lệnh , làm cho hệ thống nhầm lẫn giữa user input và instruction 

- okay , reseach ta có 1 vài cách để nối dài : ; & || %0a ( %0a = new line )

- ta thử câu lệnh 1.1.1.1 ; cat index.php

![Alt text](<../image/22.2.png>)

- uhm có thêm 1 khung nhập vậy đúng là đã kéo được source thằng index.php 
- ae view source để xem chi tiết hơn 

![Alt text](<../image/22.3.png>)

- nó comment $flag = file_get_content(.passwd)
- nên ta sẽ đọc thằng .passwd để lấy flag 

![Alt text](<../image/22.4.png>)

- lụm cờ :> 

#hackerga2101: 
- command inject là một loại lỗi rất nguy hiểm vì nó có thể thực thi câu lệnh bên server 
- phải thật sự cẩn thận khi code những hàm system() , eval() , passthru() ,...
- cái lỗi này hacker lỏ nào cũng thích nè :>>
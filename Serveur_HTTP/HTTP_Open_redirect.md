- tiêu đề : HTTP - Open redirect = chuyển hướng cởi mở :>
- nội dung : tìm cách chuyển hướng đến một tên miền khác với những cái chỉ định 

- lại là công cuộc dùng thử 
- lúc vào giao diện thì ae được chọn 3 mục Facebook , Twitter , Slack 
- thao tác thử thì nó sẽ redirect đến 3 trang kia

- vậy để biết xem nó redirect kiểu gì thì bật burpsuite mode thoii

![Alt text](<../image/3.1.png>)

- uhmm nó có 2 tham số Get url= tên miền và h= dãy số ( cảm nhận không quy tắc khả nghi là md5 hash )

- thinking : vì mấy trang kia rất rất nổi tiếng nên nếu mã kia là hash thì sẽ search được
- cầm thử google thoii ( ae cứ parse thẳng vào google )

![Alt text](<../image/3.2.png>)

- correct nó đúng là md5 hash 

- nhìn lại nội dung bài nó muốn mình redirect đến một tên miền khác 
- vậy thử redirect đến youtube xem 
- trước tiên là search hash youtube đã 

![Alt text](<../image/3.3.png>)

- okaay giờ cầm thay trường url và h trong burpsuite 
- note : anh em copy parse đừng thiếu dấu gì nhé :>

![Alt text](<../image/3.4.png>)

- redirect xong có flag luôn không cần làm gì nựa 

#hackerga2101:
- gì không biết ta hỏi google :> 
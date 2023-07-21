- tiêu đề : HTTP - Verb tampering : giả động từ ? :v
- nội dung : bỏ qua cơ chế bảo mật 

- lại một bài dạng bỏ qua bảo mật http authentication 
- vừa vào web chúng ta có 1 form auth login và như đã gặp ta nên dùng burp để xem 

![Alt text](<../image/10.1.png>)

- thử đăng nhập gà bắt lại gói tin , phần response có header WWW-Authenticate: Basic realm="My Realm"
- liên tưởng bài trước thử thêm vào http request gửi lại 

![Alt text](<../image/10.2.png>)

- nhưng kết quả là không 
- vậy thử đổi method test xem và đúng dự tính khi đổi sang OPTIONS 

![Alt text](<../image/10.3.png>)

- ae không nhất thiết phải thêm WWW-Authenticate: chỉ cần đổi method đi là được 

#hackerga2101: 
- khi làm việc với gói tin http phải luôn nhớ đâu là untrusted data ( phần mình thao túng được )
- kết hợp bài cũ để giải bài mới 
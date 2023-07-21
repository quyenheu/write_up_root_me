- tiêu đề : HTTP - POST = 1 method ae của GET , HEAD , PUT , OPTIONS , ...
- nội dung : tìm cách để vượt top score

- view qua thì web cho anh em thử điểm give a try = random điểm rồi POST lên so sánh với 999999 ( ý tưởng ấn cho liệt chuột :> ) 

![Alt text](<../image/8.1.png>)

- trong inspect cũng không có hint gì nên mở burp bắt gói tin xem thử

- mình thấy có 1 gói tin POST gửi đi khi ấn give a try 
- bắt lại thì có một content POST score=123456 ( đương nhiên là bé hơn 999999 ) và generate=give+a+try
- vậy sẽ ra sao nếu ta sửa score lớn hơn 999999 rồi gửi đi 

![Alt text](<../image/8.2.png>)

- đương nhiên là sẽ win roii

#hackerga2101: 
- như đã nói trong bài trước , gói tin http chứa rất nhiều untrusted data ( source ) và method cũng là 1 trong số đó 
- bạn nên thử thay đổi method xem có được chấp nhận không , vì mỗi method có 1 sức mạnh riêng ( sức mạnh not allow :> )


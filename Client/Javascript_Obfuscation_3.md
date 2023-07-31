- tiêu đề : Javascript - Obfuscation 3 
- nội dung : hữu dụng hay vô dụng là câu trả lời :v vô dụng zl

- vừa vào thì ae có form nhập pass . cứ nhập đi vì kiểu gì nó cũng cười vào mặt thoi :> 
- view source có ngay file js 

![Alt text](<../image-client/9.1.png>)

- thường mình sẽ lấy quảng sang web code online để đọc :> 

- đọc qua thì mình thấy cũng k có gì lắm vì ae nhập gì nó cũng cười th ( decode đống số kia ra )

- để ý có pass_enc hơi gì đó ( vì lúc vào mình để password trống )

![Alt text](<../image-client/9.2.png>)

- alert ra 1 dãy số gì gì đó 

- cùng phân tích chút thằng js này : 
   + nó nhận user input qua promt 
   + sau đó gọi lại hàm dechiffre( user input )
   + vậy tức là pass_enc = user input 
-> nhưng khi mình để trống nó lại ra 1 dãy gì đó 

![Alt text](<../image-client/9.3.png>)
- có vẻ là mặc định sẵn của biến pass_enc và nó là password cần tìm 

![Alt text](<../image-client/9.4.png>)

- mình dịch hộ r é cầm pem flag th 

#hackerga2101: 
- clien chả có gì chia sẻ :v 
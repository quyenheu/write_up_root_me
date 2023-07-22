- tiêu đề : PHP - type juggling = tà lăng 
- nội dung : PHP so sánh yếu , login thành công 

- lại là công cuộc dùng thử 
- ae vào sẽ có 1 form login và 1 link ( source code )
- mình thử login trước với admin:admin

![Alt text](<../image/25.1.png>)

- đương nhiên fail :v 
- giờ vào đọc source 

![Alt text](<../image/25.2.png>)

- như nội dung : chúng ta thấy luôn 2 lỗi so sánh trong source == và strcmp 
- vậy là nhắm được luôn chỗ cần target 

- burpsuite mode on nào : 

![Alt text](<../image/25.3.png>)

- gói tin đang POST 1 biến auth với value json 
- ae bôi đen thì góc bên phải nó tự dịch nhé , và ta cũng chỉnh sửa bên đó luôn 

- Xử Lý : với == thì để true là bypass , vậy còn strcmp ? 
- gì không biết ta hỏi google 

![Alt text](<../image/25.5.png>)
- có khá nhiều kiểu để bypass nhỉ , password thì là string vậy nên mình thử chọn array đi 

- mình sẽ sửa bên json "admin" thành true , sha256 thành [] ( ae nhớ bỏ "" không là thành string đấy ) . ấn vào Apply changes 
- pem 

![Alt text](<../image/25.4.png>)

- vổ tay , lụm cờ :> 

#hackerga2101:
- so sánh yếu vẫn luôn tồn tại và lộng hành như 1 vấn nạn :v 
- thầy mình luôn khuyên là đọc tài liệu PHP trên trang chính chủ luôn , bao uy tín và đầy đủ 
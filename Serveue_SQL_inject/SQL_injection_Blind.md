- tiêu đề : SQL injection - Blind = SQL leesin 
- nội dung : lấy password admin 

- ae chưa hiểu về tính năng intruder trong burp thì lục lại bài cũ t có hướng dẫn nhé , t cũng đ nhớ bài nào :v 

- okay web có form login và khi bạn thử thì đương nhiên no such username/password 

![Alt text](<../image/33.1.png>)

- vì là lab ctf nên mình suy đoán luôn câu lệnh query sẽ kiểu : 
- SELECT * FROM users FROM username='$_GET['username']' AND password='$_GET['password']'
- thử nghiệm nếu bạn để : admin' or 1=1 --a sẽ login được vào ( đương nhiên trang admin cũng không có mật khẩu )

- giờ chúng ta đã có tín hiệu để blind : 
   + sai -> no such 
   + đúng -> login được 

- trước tiên bắt lại gói tin bằng burp 

![Alt text](<../image/33.2.png>)

- sửa đổi trường username với câu lệnh : admin' AND passowrd='a%' --a 
- cho ae chưa biết thì a% đại diện cho a + với tất cả ký tự đằng sau 
-> câu lệnh này có nghĩa là từ đầu tiên của password có bằng a không 

![Alt text](<../image/33.3.png>)

- gửi qua intruder và sửa lại tham số 

![Alt text](<../image/33.5.png>)

- mình sẽ thử trước với dãy kí tự a-z A-Z 

![Alt text](<../image/33.4.png>)

- để ý length và thành công tìm ra ký tự đầu tiên 

- Vì password có thể dài nên tối ưu là code lại py để bruteforce -> ae tự làm nhé t lười zl :> 
- MẸO : anh install cái copy as python-request trong burp store -> rồi chuột phải gói request -> extension -> copy as python-request -> pasre vào VScode sửa lại xíu là dc 

#hackerga2101:
- trong burp store có tích hợp một số thứ hay ho zl ae nên tìm hiểu thêm 
- code python bruteforce siêu cơ bản với 'copy as python-request' :v ( mà khuyên ae nên tự code cho quen )
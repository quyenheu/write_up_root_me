- tiêu đề : HTTP - Improper redirect = chuyển hướng sai cách 
- nội dung : đừng tin browser :v vào được trang index 

- mới truy cập vào chúng ta sẽ được chuyển đến trang login /login.php?redirect ( khá phổ biến nếu chưa login trước đó thì chuyển đến trang login )

![Alt text](<../image/9.1.png>)

- vì ở chương HTTP nên mình lười test lỗi khác :>
- để ý thấy para redirect , phải chăng nó là thứ để chuyển hướng chúng ta 
- giờ cứ test thay login.php -> index.php , vì login nên lại bị redirect về login.php 

- vậy thử xóa bỏ phần ?redirect thì sao ? 
- mình xóa para và truy cập vào index.php 

![Alt text](<../image/9.2.png>)

- okay , có flag luôn 
- có vẻ họ làm redirect hơi cùi 

#hackerga2101:
- đặt thật nhiều giả thiết là bản năng nên có của hacker lỏ :>
- và đừng ngại test giả thiết của mình 
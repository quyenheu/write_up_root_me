- tiêu đề : PHP - Serialization = 1 lỗi advanced nhé
- nội dung : login với quyền admin

- NOTE : nếu ae chưa hiểu về serialization thì nên học trước chứ xem cũng khó lòng hiểu được 
- NOTE : và vì là lỗi advanced nên mình không giải thích lan man nhé :> thanks 

- test thử đã nào 
- vào web ta có 1 form login và 1 dòng link ( source code - serialization không source thì vô vọng lắm :v )
- thử login admin:admin 

![Alt text](<../image/24.1.png>)

- và đương nhiên là fail 

![Alt text](<../image/24.2.png>)

- mở burp mode lên th 
- ae thử login với tài khoản demo guest:guest để xem bên trong có gì nhé 

![Alt text](<../image/24.3.png>)

- mình mở source ra đọc và phân tích 

![Alt text](<../image/24.4.png>)

- phân tích những chỗ mình note : 
- trước tiên thì password được sha256
- nếu POST[password] hoặc POST[login] không tồn tại thì nó check xem có COOKIE[autologin] không và unserialize cái value của COOKIE đó gán biến $data
- trong if tiếp theo nó lấy dữ liệu trong mảng $data để so sánh ( chỗ này so sánh == có thể bypass được )
- nếu có POST[autologin]===1 thì nó sẽ serialize cái biến $data ra 

![Alt text](<../image/24.6.png>)

- đoạn source code bên dưới . nếu $_SESSION[login] === 'superadmin' thì require_one( admin.inc.php ) -> đây là mục tiêu của mình 

- okayy , giờ đã hiểu luồn hoạt động rồi ae khai thác thoii

- mình muốn lấy form serialize nên thêm POST[autologin]=1

![Alt text](<../image/24.5.png>)

- nhận được form serialize , lên mạng search bảng so sánh yếu của php mình biết rằng : string == boolean 
- và login ở đây phải là 'superamdin' nhé 
- sửa lại form serialize : a:2:{s:5:"login";s:10:"superadmin";s:8:"password";b:1;} decode url trước khi pem nhé 

![Alt text](<../image/24.8.png>)

- ae thêm serialize đã chuẩn bị vào Cookie: autologin=.. như hình 
- lưu ý là phải để trường password hoặc login trống nhé vì để kích hoạt được lệnh else if ( unserialize ) 
- pem và lụm cờ thoi 

#hackerga2101:
- serialization login zl hay và cuốn lúc giải nhưng vì là lỗi advanced nên đòi hỏi ae phải chắc kiến thức xíu 
- là hacker gà nên thực tế mình cũng chưa khai thác được lỗi này bao giờ :v toàn ctf thôi 
- không source đố m serialize ( ca dao tục ngữ :v ) - mà chỉ đúng với mình là hacker gà th nhé hehe



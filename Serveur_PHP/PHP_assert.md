- tiêu đề : PHP - assert() = hàm assert()
- nội dung : tìm và exploit vul để đọc .passwd file 

- NOTE : ae tìm đọc assert() và cách sử dụng với strpos trước nhé 
- view qua web có 3 mục home , about , contact 
- đặc biệt hơn là para page= 

![Alt text](<../image/27.1.png>)

- ../ everywhere thoi :> 

![Alt text](<../image/27.2.png>)

- yeh có lỗi văng ra ròi 
- phân tích một chút , mình nghĩ code sẽ như sau : assert("strpos('includes/../.php,'..')===false) 
- nó sẽ ban bạn nếu có .. còn không ví dụ nhập là home thì include(home.php)

- okay hiểu luồng hoạt động rồi , ae exploit thoi 
- mình sẽ inject 'and die(show_source('.passwd')) or '
- tại sao thì để code kia sẽ thành assert("strpos('includes'' and die(show_source('.passwd')) or '.php,'..')===false)
- ae ngẫm lúc nhé cho hiểu :> 


![Alt text](<../image/27.3.png>)

- pem , lụm cờ lụm cờ 

#hackerga2101: 
- thử bằng kinh nghiệm sẽ cho ae nhiều hướng đi mới , ngồi nghĩ nhiều đau đầu lắm :v 
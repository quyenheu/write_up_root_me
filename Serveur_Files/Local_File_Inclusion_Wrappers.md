- tiêu đề : Local File Inclusion - Wrappers = bài trước mình có bảo ae tìm hiểu thêm URI wrappers 
- nội dung : get flag :v 

- bài này khá quằn để giải thích vì lúc mình làm phải test khá nhiều 

- vào up thử ảnh và nhận được 2 trường para : 

![Alt text](<../image/20.1.png>)

- PHẦN TEST : 

- ../ everywhere và hack detected

![Alt text](<../image/20.2.png>)

- test thêm chút nữa mình thấy rằng trường para page khi thêm một số ký tự sẽ bị ban ví dụ . / % v.v 
- còn thằng para id thì không ảnh hưởng nhiều 

- ta thử encode xem có được không 

![Alt text](<../image/20.4.png>)

- no , nếu không path traversal được ta thử làm wrappers xem 
- test tiếp thì nó ban không chừa thằng nào :> thật ra là còn thằng zip 
- nhưng upload này không cho zip lên ? vậy thì xử lý kiểu gì 
- ae nghĩ , sẽ ra sao nếu ta có 1 file zip chứa file php với nội dung show_source('index.php') và đổi tên nó thành jpg upload lên :> ảo ma vch 
- test thử nhé 

- NOTE : tên của cái zip mình tải lên là trường para id đằng sau 
- sau khi upload lên như trên ta nhận được source code 

![Alt text](<../image/20.5.png>)

- sau khi nhận được source là chứng mình ta đã thực thi được code PHP
- giờ up shell lên hoi , anh đổi nội dung file PHP thành system() , eval() thử mà xem kiểu gì cũng bị ban :> 

- bọn này nó cấm không chừa thằng nào 
- nhưng trong PHP còn 1 cách list all file nữa = code : 

<pre>

<?php

$path = './';

$files = scandir($path);

foreach($files as $file) {

echo "<a href='$file'>$file</a>";

}

?>

</pre>;

- giờ thấy thằng file chứa flag roi 

![Alt text](<../image/20.6.png>)

- get thoi 

![Alt text](<../image/20.7.png>)

#hackerga2101: 
- bài này kết hợp khá nhiều kỹ thuật có thể nói là khó ( rễ-tôi khó zl mà :> )
- có gì không hiểu cứ contact mình qua ig ( README.md ) nhé 

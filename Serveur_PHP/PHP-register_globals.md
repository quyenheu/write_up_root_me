- tiêu đề : PHP - register globals
- nội dung : đọc flag :> 

- uhm bài này tool tủng tí nhee :> fuzz qua thì sẽ có 1 đường dẫn /index.php.bak 

![Alt text](<../image/36.1.png>)

- okay down dc source rồi 
- ae đọc source sẽ thấy có đoạn code register_global bị lỗi ( thật re lúc đầu mình cứ nghĩ là weak compare hehe xong đọc lại đề bài )
- okay sơ qua lỗi register_global như sao : 

" if (!ini_get('register_globals')) { ... }: Đây là một phần quan trọng của mã, nhưng cũng là một phần có thể gây rủi ro bảo mật. Nó kiểm tra xem tùy chọn PHP register_globals có được kích hoạt hay không. Nếu tùy chọn này không được kích hoạt, nó sẽ thực hiện việc trích xuất giá trị từ các biến siêu toàn cục (superglobals) như $_SERVER, $_ENV, $_FILES, $_COOKIE, $_POST, $_GET, và $_SESSION, và gán chúng vào các biến cục bộ. Điều này có thể gây ra nhiều vấn đề bảo mật và xung đột tên biến " 

- hehe gpt ấy 
- vậy giờ còn bước kích hoạt 

![Alt text](<../image/36.2.png>)

- pem và lụm cờ 

#hackerga2101: 
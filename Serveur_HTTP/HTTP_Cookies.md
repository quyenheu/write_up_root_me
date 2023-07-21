- tiêu đề : HTTP - Cookies = bánh quys 
- nội dung : ông bob này yêu bánh quy , và bob tạo ra script php để lấy user email 

- view thử web , ta có 2 tính năng : send và saved email address

![Alt text](<../image/11.1.png>)

- dùng thử 2 tính năng này thì saved email address bị hạn chế do mình không phải admin 

- xem source có một comment : Setcookie("ch7","visiteur") là một hàm trong PHP để set giá trị cookie 

![Alt text](<../image/11.3.png>)

- qua mục application và xem cookie 

![Alt text](<../image/11.4.png>)

- mình đoán visiteur = visiter :v nên đã thử thay nó bằng admin xem có sự phân biệt đối xử nào ở đây không 

![Alt text](<../image/11.5.png>)

- okkay , có flag rồi 

#hackerga2101: 
- Cookie rất quan trọng , nó thường ảnh hưởng đến qua trình bypass authen nên ae tìm hiểu thêm nhé 
- Cookie là 1 untrusted data ae có thể thao túng nó ngay trên dev tool và trong burp 
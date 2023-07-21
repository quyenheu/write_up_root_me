- tiêu đề : HTTP - Headers 
- nội dung : phần http response có thêm thông tin + được admin access vào web 

- dùng thử nào 
- lại là web có mỗi dòng chữ :v Content is not the only part of an HTTP response!

![Alt text](<../image/7.1.png>)

- view qua source , cookie cũng không thấy có gì 
- burpsuite mode thoi

![Alt text](<../image/7.2.png>)

- như hint trên thì mình đọc response thấy có 1 header khá lạ Header-RootMe-Admin: none
- mình suy đoán rằng chắc nó ảnh hưởng đến quyền truy cập
- vậy nó có thể thêm vào request không 
- mình thử thêm trường này vào request với giá trị admin 


![Alt text](<../image/7.3.png>)

- bom , có luôn flag 
- NOTE : bạn có thể thử với bất cứ giá trị nào không phải admin 

#hackerga2101: 
- để ý các header bên response sẽ cho bạn thêm nhiều thông tin và ý tưởng để khai thác 
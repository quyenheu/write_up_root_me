- tiêu đề : Remote File Inclusion = thực thi file inclusion từ xa 
- nội dung : đọc được source index.php 

- view web lúc thì thấy có mỗi para là nổi bật nhất 

![Alt text](<../image/19.1.png>)

- mình đoán nó nhận tham số để thay đổi ngôn ngữ 
- mình thử thay đổi thành Vi xem sao 

![Alt text](<../image/19.2.png>)

- uhm có dấu hiện rồi đây hàm include(vi_lang.php)
- chắc _lang.php là nó tự thêm vào 

- okay đại khái include() kiểu nó kéo tag PHP về và thực thi 

![Alt text](<../image/19.3.png>)

- okay vậy là có được code index.php dạng base64 
- ae mang decode ra là win 

![Alt text](<../image/19.4.png>)

- get flag 

#hackerga2101: 
- ae nên tìm hiểu cách hoạt động của hàm include() trong PHP và file URI wrappers


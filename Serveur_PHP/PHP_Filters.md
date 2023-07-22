- tiêu đề : PHP - Filters = máy lọc nước kangaroo
- nội dung : tìm password 

- FUN FACT : nhìn từ filter mình cứ nghĩ nó filter code cái gì cơ , me nó tốn thời gian nghĩ :>>

- view web tí nào , ta có 2 trang login và home
- và đặc biệt hơn là para inc=login.php ( liên tưởng file .inc và hàm include() )

![Alt text](<../image/26.1.png>)


- okay mình test thử thay hackerga vào login.php

![Alt text](<../image/26.2.png>)

- misconfig này , 1 đống lỗi tha hồ phân tích 
- đúng như dự đoán nó đang include thẳng các file php lại 
- giờ mình mới nghĩ ra cái từ filters của tiêu đề là gì :> 
- táng wrappers vào đọc source th : php://filter/convert.base64-encode/resource=login.php

![Alt text](<../image/26.3.png>)

- decode base64 

![Alt text](<../image/26.4.png>)

- thấy nó có include config.php
- mình làm lại bước trên để đọc config.php

![Alt text](<../image/26.5.png>)

- decode base64 

![Alt text](<../image/26.6.png>)

- gett flag :> 

#hackerga2101:
- bài này chia sẻ kinh nghiệm me gì ta :v
- uhm chắc là para ở đâu thì táng thử hết ở đó :> 
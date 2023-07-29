- tiêu đề : SQL injection - Error 
- nội dung : lấy mật khẩu admin 

- NOTE : mình làm sẽ test nhiều bước nhưng đây là wu nên khai thác thẳng luôn nhé 

- đầu tiên view qua web ae có 1 trang login và contents

![Alt text](<../image/35.1.png>)

![Alt text](<../image/35.2.png>)

- mình inject thử ' ở chỗ order trong trang contents và nhận được lỗi syntax 
- có vẻ họ tự thêm dấu ' nữa 

![Alt text](<../image/35.3.png>)
- mình thấy được câu truy vấn chính rui : select * from contents order by pase + '$_GET['order']'

- ở bài time-base mình có chia sẻ về 1 số hàm khá thú vị trong SQL
- và bài này ae phải hiểu về 2 thứ đó là ORDER BY và hàm CAST() 

- okay trước tiên mình tìm tên bảng : 
  + , cast((select table_name from information_schema.tables limit 1 ) as DATE ) --a 
  + mình thêm limit vì từng thử rồi nếu không limit 1 sẽ bị error khác cột 
  + ngoài DATE ra ae có thể để dạng khác nếu convert được 

- mục đích khi mình làm việc này không phải để nó trả về kết quả trong câu truy vấn chính mà để nó văng ra kết quả ở lỗi nhé 

![Alt text](<../image/35.5.png>)

- tiếp đến là tìm cột : 
  + , cast((select column_name from information_schema.columns limit 1 offset 2 ) as DATE ) --a
  + lần đầu sẽ ra id vì mình limit 1 ( tại sao không sử dụng group_concat thì nó không tồn tại nhé )
  + tiếp đến thêm offset 2 thì thấy được cái column giống password 

![Alt text](<../image/35.6.png>)

- select vào nó lấy dữ liệu thôi 

![Alt text](<../image/35.7.png>)

- và đây chính là password cần tìm 
  + tại sao ? vì trong bảng này có mỗi account admin thôi :> mình thử rồi nên biết 
  + ae có thể chứng mình cái ý kiến trên của mình để hiểu hơn về bài này nhé 

#hackerga2101:
- tìm hiểu 1 số hàm hỗ trợ trong mysql như: length, substr, group_concat, cast, ...
- và các option select: limit, offset, ... 

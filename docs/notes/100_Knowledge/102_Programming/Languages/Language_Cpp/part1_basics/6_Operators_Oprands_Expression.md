---
categories:
  - cpp-language
fileClass:
  - series
share: true
---


series:: [lang_cpp](../Language_Cpp.md)
order:: 6

# Biểu thức, toán tử, toán hạng
## Biểu thức

> [!definition] Định nghĩa
> Biểu thức là một dãy hữu hạn các phép biến đổi toán học để tạo ra một giá trị từ các giá trị ban đầu

VD:
- `2+3*4` là một biểu thức
- `4+5*3-24-1+a` là một biểu thức
- `a+b` là một biểu thức
Biểu thức có 2 thành phần: **toán tử** và **toán hạng**
## Toán hạng

> [!definition]
> Toán hạng là các con số, biến và hằng được sử dụng trong biểu thức.

VD:
`1+2` thì `1` và `2` là toán hạng
`2/a` thì `2` và `a` là toán hạng
## Toán tử
> [!definition] Định nghĩa
> Toán tử là các cách làm việc với toán hạng để tạo thành biểu thức. Các toán tử thường được biểu thị dưới dạng các kí tự để dễ học, hiểu và nhớ

### Quyền ưu tiên và thứ tự thực hiện biểu thức

- Quyền ưu tiên cho cho phép sắp xếp và thực hiện biểu  thức theo một thứ tự nhất định
- Thứ tự thực hiện đề ra thứ tự thực hiện với các toán tử có cùng độ ưu tiên
- Bảng về quyền ưu tiên và thứ tự của các toán tử được trình bày tại [https://www.learncpp.com/cpp-tutorial/operator-precedence-and-associativity/](https://www.learncpp.com/cpp-tutorial/operator-precedence-and-associativity/)

### Các loại toán tử

Có 5 loại toán tử chính thường được sử dụng:
- Toán tử một ngôi unary: sử dụng với duy nhất một toán hạng. VD: +, -, sizeof    
- Toán tử hai ngôi binary: sử dụng với 2 toán hạng
VD: `+,-,*,/,…`
- Toán tử tăng giảm: dùng để tăng hay giảm giá trị của một toán hạng VD ++, --
- Toán tử bitwise: dùng để thao tác bit
- Các loại toán tử còn lại

### Các toán tử số học
- Các toán tử số học bao gồm các phép toán cơ bản như cộng (`+`), trừ(`-`), nhân(`*`), chia(`/`), chia lấy dư(`%`),… Các phép toán khác được cung cấp sẵn bởi C++ trong các hàm, thường được định nghĩa trong thư viện `<cmath>`

### Các toán tử gán
Là các toán tử dùng để gán giá trị bên phải cho giá trị bên trái bao gồm:
`x=y` : gán giá trị của y cho x;
`x+=y`: tăng x thêm y đơn vị
`x-=y`: giảm x đi y đơn vị
`x*=y`: gán `x*y` cho x
`x/=y`: gán `x/y` cho x
`x%=y`: gán `x%y` cho x

### Toán tử tăng giảm
Đa số các ngôn ngữ lập trình sử dụng 2 toán tử ++ và -- để tăng/giảm giá trị của một biến đi 1. Tuy nhiên, sẽ có một số sự khác biệt dựa trên vị trí của toán tử này:

- `c++` : sao chép biến c, tăng c thêm 1, rồi trả về bản sao của c
- `++c`: tăng c thêm một, rồi trả về c
Điều tương tự xảy ra với `--`
VD:
Xét chương trình sau:

> [!code]
> ```cpp
> int c(3);//(1)
> int C(3);//(2)
> int d = c++;//(3)
> int D = ++C;//(4)
> std::cout << c << " " << C << " " << d << " " << D;
> ```
> 

sẽ xuất ra `4 4 3 4`. Tại sao vậy?
- Trong câu lệnh (3), giá trị của c được gán cho d rồi c mới tăng lên
- Trong câu lệnh (4), giá trị của C tăng lên rồi mới gán cho D
Vì vậy, mặc dù không khác nhau nhiều, nhưng chúng ta nên sử dụng ++var để tăng hiệu suất làm việc và tránh sai sót.
### Toán tử điều kiện
Được coi là “dạng số học” của câu lệnh if-else, toán tử điều kiện có công thức tổng quát như sau:

>[!formula] Cấu trúc toán tử điều kiện
>`C ? T : F`
>
>C: điều kiện
>T: giá trị trả về nếu C đúng
>F: giá trị trả về nếu C sai

Lưu ý: nên dùng ngoặc đơn để biểu thị điều kiện
VD:
`M=(x>y)?x:y`
Nghĩa là:
- Nếu x>y thì gán x cho M
- Ngược lại gán y cho M
Câu lệnh trên thường dùng để tìm số lớn hơn trong hai số x và y
### Toán tử quan hệ
- Toán tử quan hệ giữa hai toán hạng dùng để biểu thị quan hệ số học giữa hai toán hạng và trả về một trong hai giá trị True và False.
- Có 6 toán tử quan hệ trong C++, dựa trên các phép so sánh hai số:
	- `>`: lớn hơn
	- `<`: nhỏ hơn
	- `<=`: nhỏ hơn hoặc bằng
	- `>=`: lớn hơn hoặc bằng
	- ` == `  : bằng
	- `!=`: khác

Sử dụng toán tử quan hệ để so sánh 2 số nguyên thường trả về kết quả chính xác. Nhưng với các số thực chấm động thì không như vậy. VD:

`0.3==0.1+0.2` trả về `False`

Lí do là bởi vì [lỗi làm tròn số chấm động](l%E1%BB%97i%20l%C3%A0m%20tr%C3%B2n%20s%E1%BB%91%20ch%E1%BA%A5m%20%C4%91%E1%BB%99ng.md) trong C++. Vì vậy, để so sánh hai số chấm động ta nên xét hiệu của chúng nhỏ hơn một giá trị nào đó(epsilon)

VD:
`0.3 - (0.2 + 0.1) < 0.00001 = true`

### Toán tử logic
Toán tử logic thường sử dụng với các kiểu dữ liệu Boolean. Có 3 toán tử logic chính:
- `!a`: nếu a false thì trả về true
- `a && b`: nếu a và b cùng true thì trả về true
- `a || b`: nếu a hoặc b là true thì trả về true
Lưu ý:
- Khi sử dụng toán tử AND &&, nếu toán hạng bên trái =false thì chương trình sẽ tự động cho biểu thức là false, nên toán hạng bên phải sẽ không được tính toán. Vì vậy nếu toán hạng bên phải chứa toán tử tăng giảm thì có thể toán tử đó sẽ mất tác dụng
VD:

> [!code]
> 
> ```cpp
> int x(3);
> int y(2);
> bool m = (x == 1) && (++y == 3);
> std::cout << y;
> ```
> 
> sẽ xuất ra 2. 

Toán tử ++ với toán hạng y đã bị bỏ qua

- Định luật De Morgan:
    

Định luật De Morgan sử dụng trong việc kết hợp các toán tử logic tránh cho lập trình viên nhầm lẫn khi sử dụng

Ta có:

!(x && y) tương đương !x || !y

!(x || y) tương đương !x && !y

12. Một số toán tử khác
    

Tham khảo [https://www.learncpp.com/cpp-tutorial/operator-precedence-and-associativity/](https://www.learncpp.com/cpp-tutorial/operator-precedence-and-associativity/)
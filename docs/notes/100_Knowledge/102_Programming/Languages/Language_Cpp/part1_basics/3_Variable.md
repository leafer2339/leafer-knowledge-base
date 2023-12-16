---
subject: 
categories: 
tags:
  - programming
fileClass:
  - series
share: true
---


series:: [lang_cpp](../Language_Cpp.md)
order:: 3

# Biến
## Biến là gì
>[!code] Định nghĩa
> - **Biến** là một vùng trong bộ nhớ RAM để lưu trữ thông tin, chương trình có thể truy cập vùng nhớ này để lấy và truy xuất thông tin.

- Ví dụ, nếu x là một biến, sẽ có một vùng trong bộ nhớ RAM được cấp phát cho nó. Chương trình có thể truy cập vùng nhớ này để biết những thông tin biến x đang chứa
## Khai báo biến
- Để sử dụng một biến, ta cần khai báo(declare) biến đó. Cú pháp khai báo biến như sau:
```
DT name
```
- Trong đó:
	- DT(data type): là kiểu dữ liệu của biến, trong C++ có rất nhiều kiểu dữ liệu như `int`, `float`, `char`,…
	- `name` là tên của biến, tuân theo một số quy tắc sau:
		- Chứa các chữ cái thường (từ a đến z), các chữ cái hoa(từ A đến Z), cái chữ số(từ 0 đến 9) và dấu gạch dưới
		- Bắt đầu bằng các chữ cái hoặc dấu gạch dưới
		- Không chứa dấu cách(backspace)
		- Không trùng với các từ khóa có sẵn của C++
		- Không trùng với các biến đã khai báo
		- Ngoài ra, tên trong C++ phân biệt chữ hoa và chữ thường, vì thế ab, Ab, AB, aB là 4 biến khác nhau
## Khởi tạo biến
- **Khởi tạo biến(initialization)** là gán cho biến một giá trị nào đó.
- Khởi tạo sao chép: Là cách khởi tạo sử dụng phép toán “=”, thông tin sẽ được _sao chép_ từ vế phải sang vế trái
VD:
```cpp
int x;
x=5;//5 được sao chép vào biến x
```


- Khởi tạo trực tiếp: Là cách khởi tạo sử dụng 2 sấu ngoặc tròn ()
VD:
```cpp
int x(5);
```

- Khởi tạo trực tiếp khá giống khởi tạo sao chép. Với những kiểu dữ liệu đơn giản, 2 kiểu khởi tạo này như nhau, nhưng với những kiểu dữ liệu phức tạp hơn, khởi tạo trực tiếp cho hiệu suất tốt hơn. Khởi tạo trực tiếp còn được sử dụng trong lập trình hướng đối tượng. Xem thêm Constructor

- Khởi tạo đồng nhất(C++11 trở đi): tuy nhiên, khởi tạo trực tiếp ko hiệu quả với tất cả những loại khởi tạo. Vì vậy từ C++11 trở đi chúng ta được cung cấp thêm một kiểu khởi tạo mới:
VD:
```cpp
int x{5};
```

- Khởi tạo đồng nhất dùng để khởi tạo một danh sách dữ liệu vd 
```cpp
int x{1,3,4,5}.
```

```cpp
int x{4.5}
```
sẽ gặp lỗi mặc dù với 2 cách khởi tạo trên, 4.5 sẽ được ép kiểu về 4 và được sao chép về biến x. Xem thêm Ép kiểu. Nhưng với khởi tạo đồng nhất, do 4.5 có kiểu dữ liệu khác với int nên sẽ gây ra lỗi

## Phạm vi của biến
>[!code] Định nghĩa
>Phạm vi của biến(scope) là thời gian biến có thể được sử dụng, được tính từ khi biến được khai báo cho đến khi biến bị hủy.

Ví dụ:
```cpp
{
int x;//biến x được khai báo
//x được sử dụng tại đây
//x bị hủy
}
//tại đây, x ko còn được sử dụng
```

Có rất nhiều phạm vi sử dụng của biến, xem thêm trong những bài sau.

## Địa chỉ của biến
>[!code] Định nghĩa
>- Địa chỉ của biến là vùng bộ nhớ RAM mà biến nắm giữ. 
>- Để lấy địa chỉ của biến ta có thể dùng phép toán địa chỉ &

VD: `&x` cho địa chỉ của biến `x`
Địa chỉ của biến có thể _được chứa trong một biến khác_, gọi là **[Con trỏ](24_Pointers.md)**.

## Biến tham chiếu
- Giả sử ta có 2 biến x và y. 
- Mặc dù ta sử dụng x=y nhưng khi x và y thay đổi thì biến còn lại không thay đổi vì _địa chỉ_ của x và y khác nhau. 
- Biến tham chiếu là biến cho phép khi nó thay đổi thì biến được tham chiếu cũng thay đổi. Để khởi tạo biến tham chiếu ta sử dụng:

>[!code] Cú pháp khai báo biến tham chiếu
>```
>Kiểu dữ liệu &tên biến tham chiếu=tên biến được tham chiếu
>```

VD: `&a=b` –> a là biến tham chiếu của b, khi a thay đổi thì b cũng thay đổi.


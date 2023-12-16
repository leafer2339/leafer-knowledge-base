---
categories:
  - cpp-language
fileClass:
  - series
share: true
---


series:: [lang_cpp](../Language_Cpp.md)
order:: 5

# Các kiểu dữ liệu cơ bản trong C++
## 1. Kiểu số nguyên integer

- Một biến thuộc kiểu số nguyên có thể chứa các giá trị là số nguyên bao gồm các số nguyên âm, nguyên dương và số 0

- Có 4 loại số nguyên trong C++ là `short`, `int`, `long` và `long long`, mỗi loại sẽ chiếm một vùng nhất định trong bộ nhớ, được trình bày trong bảng sau:


|Loại|Kích thước|Ghi chú|
|---|---|---|
|`short`|2 bytes||
|`int`|2 bytes|4 bytes trên các mô hình hiện đại|
|`long`|4 bytes||
|`long long`|8 bytes|C++11 trở đi|

  

Mỗi loại sẽ có thể lưu trữ các số nguyên từ `-2n-1` đến `2n+1` với n là kích thước của chúng tính theo bit

## 2. Kiểu số chấm động

Để lưu trữ các số thực ta có thể sử dụng kiểu float, kiểu float có 3 loại là `float`, `double` và `long double`

|   |   |   |
|---|---|---|
|`float`|4 bytes|±1.18 x 10-38 to ±3.4 x 1038|
|`double`|8 bytes|±2.23 x 10-308 to ±1.80 x 10308|
|`long double`|>= 8 bytes||


### In số chấm động ra màn hình

Một số thực khi được in ra màn hình sẽ không được in tất cả ra màn hình. VD:

> [!code]
> ```cpp
> std::cout << 1.11111111111;
> ```
> in ra 1.11111
> 

Vì C++ sẽ in ra số thực chấm động có độ rộng là 7 kí tự. Để tránh việc này có 2 cách:
- Cách của c:
Ta có thể dùng hàm  `printf("%.nf", f);` để in ra số thực f với n chữ số thập phân. Hàm này nằm trong thư viện `<cstdio>` 

- Thư viện `<iomanip>`:
Thư viện `<iomanip>` cung cấp hàm `std::setprecision(n)` đặt độ rộng của trường ra của số chấm động là n
Tuy nhiên, số chấm động có vấn đề về làm tròn, khiến cho việc tính toán và so sánh các số thực chấm động trở nên bị sai. 

## 3. Kiểu Boolean
Boolean là kiểu dữ liệu chỉ chứa 2 giá trị: Đúng và Sai. Nó dùng để chứa tính đúng sai của một biểu thức so sánh. Ngoài ra, khi truyền giá trị số vào kiểu Boolean. Nếu giá trị=0, Boolean=False, ngược lại =True. Boolean thường được sử dụng để lưu trữ giá trị của các biểu thức so sánh
## 4. Kiểu char
`char` là kiểu dữ liệu được sử dụng để lưu trữ các kí tự có trong bảng ASCII bao gồm các chữ cái in hoa, chữ số và kí tự đặc biệt. Xem thêm Bảng ASCII

Ngoài ra, dữ liệu được lưu trữ dưới kiểu char có thể được biểu diễn bằng số nguyên là mã của kí tự đó trong bảng ASCII. Vì vậy, ta có thể dùng số nguyên để khởi tạo kiểu dữ liệu char

VD:

> [!code]
> ```
> char n(97);
> std::cout << n;
> ```
> output: a . Vì mã ascii của a là 97

Ngoài các kí tự thông thường, còn có các kí tự đặc biệt, các kí từ này thường bắt đầu với dấu / và làm một công việc nhất định. Xem thêm tại [https://www.learncpp.com/cpp-tutorial/chars/](https://www.learncpp.com/cpp-tutorial/chars/)

## 5. Kiểu `void`
Void có nghĩa là không có gì cả, vì vậy sẽ không có bất cứ dữ liệu hay bộ nhớ nào được cấp phát cho nó. Khai báo biến kiểu void xảy ra lỗi. Tuy nhiên, void thường được dùng trong các hàm không trả về giá trị nào.

## 6. Toán tử `sizeof`
Sizeof() là toán tử để xác định kích thước vùng nhớ của một kiểu dữ liệu hay một biến tính theo byte. Toán tử này thường được dùng trong việc tìm số phần tử của mảng, cấp phát động trong C,…
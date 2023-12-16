---
tags:
  - lang/cpp
share: true
---


# Cơ bản về hàm (function)
## 1. Hàm là gì?

>[!definition] Định nghĩa
>Hàm(function) là một dãy câu lệnh có thể tái sử dụng được viết ra để làm một công việc nào đó.

Một chương trình C++ bắt buộc có một hàm, gọi là hàm `main()`. Mọi câu lệnh bên trong hàm `main()` sẽ được thực hiện khi chạy chương trình. Ngoài ra, lập trình viên có thể tự định nghĩa các hàm cần dùng cho chương trình của mình

## 2. Khai báo và định nghĩa hàm
>[!code] Cú pháp khai báo và định nghĩa hàm
>```
>return_type function_name(list of arguments)
>{
>//code goes here
>[return …];
>}
>```

`return_type`: kiểu dữ liệu trả về
`function_name`: tên hàm
`list of arguments`: các tham số tham gia vào việc thực hiện hàm

## 3. Lời gọi hàm
### a. Tổng quát:
Function_name(list of parameter);

Function_name: tên hàm

List of parameter: các đối. Chúng sẽ thay thế các tham số khi thực hiện hàm và trả về kết quả

2. Gọi hàm
    

Khi thực hiện chương trình, các câu lệnh phía trên sẽ được thực hiện trước rồi mới đến các câu lệnh phía dưới. Một lời gọi hàm sẽ báo cho CPU ra tạm ra khỏi hàm hiện tại để thực hiện hàm khác. Lúc này CPU sẽ đánh dấu phần đang thực hiện và thực hiện hàm được gọi, sau đó CPU sẽ quay trở lại phần được đánh dấu và tiếp tục chương trình.

4. Hàm trả về dữ liệu
    

Là hàm mà sau khi thực hiện, một dữ liệu nào đó sẽ được đưa ra. Để một hàm có thể trả về dữ liệu, ta cần:

- Xác định kiểu dữ liệu của giá trị trả về
    
- Sử dụng câu lệnh return trong thân hàm để ngay lập tức ra khỏi hàm và trả về dữ liệu
    

5. Hàm không trả về dữ liệu
    

Là hàm kiểu void. Hàm sẽ không trả về bất cứ dữ liệu nào, nếu thêm câu lệnh return vào thân hàm sẽ ra lỗi

6. Tham số và đối
    

1. Tham số
    

Là biến được dùng bởi hàm. Biến này sẽ có thể được thao tác trong toàn bộ hàm.

VD:

Int myFunc(para1, para2)<– tham số{

//Para1 và para2 có thể dùng tại đây

}//kết thúc hàm

Para1 và para2 không thể dùng tại đây

2. Đối số
    

Là dữ liệu được truyền cho tham số của hàm để hàm có thể xử lí chúng.

7. Tiền khai báo và định nghĩa
    

Vì trình tự thực hiện chương trình của C++ là từ trên xuống dưới nên để gọi một hàm, hàm đó phải được định nghĩa. Nên nếu hàm được định nghĩa sau hàm main() sẽ xảy ra lỗi. Nhưng nếu ta đã định nghĩa hàm plus() sau đây sau hàm main thì phải làm thế nào?

Int main(){

//code goes here

plus(1,2);

}

Int plus(int a, int b){

Return a+b;

}//error

Có 2 cách để sửa.

- Đưa hàm plus lên trên hàm main()
    

Int plus(int a, int b){

Return a+b;

}

Int main(){

//code goes here

plus(1,2);

}//ok

- Tiền khai báo:
    

Tiền khai báo là một giải pháp. Nó giống như việc ta khai báo mà không khởi tạo biến vậy. Cú pháp tiền khai báo:

Int function_name(parameters);

Function_name: tên hàm

Parameter: các tham số cần thiết

Khi đó, hàm có thể được định nghĩa sau đó. Đoạn mã sau đây sẽ không xảy ra lỗi:

Int plus(int a, int b);

Int main(){

//code goes here

plus(1,2);

}

Int plus(int a, int b){

Return a+b;

}//ok

Liên quan: 32, 33, 34, 35, 39, 41, 42

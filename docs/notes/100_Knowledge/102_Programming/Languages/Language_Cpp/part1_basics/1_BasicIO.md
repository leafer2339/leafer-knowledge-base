---
subject: 
categories: 
tags:
  - programming
share: true
---




# 1_BasicIO
## Tóm tắt

## Nguồn:


# Bài 1: Nhập xuất cơ bản C++
## 1. Thư viện `<iostream>`
Thư viện iostream là thư viện nhập xuất cơ bản của C++
Thêm thư viện sử dụng:
```cpp
#include <iostream>
```
## 2. Hàm xuất std::cout
1.  Công thức sử dụng:
    
```cpp
std::cout<<bt1<<bt2<<bt3[<<std::endl];
```
trong đó:
bt1, bt2, bt3 là các biểu thức
`std::endl` dùng để kết thúc dòng và sang dòng mới
VD:
```cpp
std::cout<<”Hello world!”;
std::cout<<”Leaf Studio”;
```
Output: 
`Hello worldLeaf Studio`
```
Std::cout<<”Hello world”<<std::endl;
Std::cout<<”Leaf Studio”;
```
Output: 
`Hello world`
`Leaf Studio`
## 3.  Hàm nhập std::cin
Tổng quát:
```
std::cin>>var_1>>var_2…;
```
Trong đó:
Var_1, var_2 là các biến cần nhập dữ liệu
VD:
```
std::cin>>n;
```
Với input 5, n sẽ nhận giá trị là 5.

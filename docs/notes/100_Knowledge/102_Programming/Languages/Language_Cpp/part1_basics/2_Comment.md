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
order:: 2

# Ghi chú
## Ghi chú là gì
- Ghi chú(comment) là những dòng lập trình viên viết ra nhưng không được biên dịch hay bị bỏ qua trong quá trình thực thi chương trình
Ví dụ:
```cpp
std::cout<<”Hello”;
//Std::cout<<”chao”; <– đây là ghi chú nên sẽ bị bỏ qua
```

```
Output:
Hello
```


## Một số cách để ghi chú trong chương trình
- Ghi chú dòng đơn: Sử dụng “//”
Ví dụ:
```
//ghi chú
```


- Ghi chú nhiều dòng: Sử dụng cặp dấu “/*” và “*/”
Ví dụ:
```
/*ghi chú dòng 1
Ghi chú dòng 2
…
*/
```

## Khi nào sử dụng ghi chú:
- Để chú thích những thứ quan trọng khi làm việc trong nhơm
- Để tạm thời “xóa” những đoạn code chưa cần thiết hoặc đang gặp lỗi
- Tạo ghi chú giúp dễ đọc, hiểu và sử dụng lại code
- Một số mục đích khác như ghi tác giả, sở hữu bản quyền, v.v.

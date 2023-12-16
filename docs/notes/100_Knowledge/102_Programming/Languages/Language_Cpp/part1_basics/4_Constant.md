---
categories:
  - cpp-language
fileClass:
  - series
share: true
---


series:: [lang_cpp](../Language_Cpp.md)
order:: 4

# Hằng

## 1. Hằng là gì?
>[!formula] Định nghĩa
> **Hằng** là một [biến](./3_Variable.md) không thể thay đổi giá trị trong chương trình

## 2. Khởi tạo hằng
Vì hằng là một biến nên cách khởi tạo cũng giống bình thường. Chỉ cần thêm từ khóa `const` vào trước dòng khởi tạo

VD:

> [!code]
> ```cpp
> const int i(3);
> ```

Khởi tạo một hằng tên là i có giá trị 3

Ngoài từ khóa `const`, ta còn có thể dùng từ khóa `constexpr`. Ví dụ:

> [!code]
> ```
> constexpr int i(3);
> ```

Cũng có tác dụng tương tự.

Sự khác nhau giữa const và constexpr:    
- `constexpr` được dùng để khai báo hằng sẽ khởi tạo khi _biên dịch chương trình_. Vì vậy, các số được đưa vào hằng `constexpr` phải xác định khi dịch chương trình
- Hằng được khai báo với const sẽ được khởi tạo khi _chạy chương trình_. Vì vậy, các giá trị được đưa vào hằng const có thể được xác định khi chạy chương trình

VD:

> [!code]
> ```
> const int d(k);//ok vì khi chạy k sẽ xác định 
> constexpr int f(k);//lỗi vì khi dịch chương trình k không xác định
> ```


Ngoài ra, còn một cách khác là sử dụng chỉ thị tiền xử lí `#define` nhưng cách này ít được sử dụng và không nên sử dụng.


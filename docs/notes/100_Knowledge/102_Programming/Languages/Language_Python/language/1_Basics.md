---
share: true
---

#programming #lang/py

categories:: python-language


# Python cơ bản
## Biến và các kiểu dữ liệu
- Python có 3 kiểu dữ liệu cơ bản nhất: `int`, `float` và `string`.
	- Kiểu `int` chứa các giá trị số nguyên.
	- Kiểu `float` chứa các giá trị số thực
	- Kiểu `string` chứa các giá trị xâu, hay dãy kí tự nằm trong dấu nháy đơn `'ví dụ như này'` hoặc dấu nháy kép `"thế này"`
- Khác với C++, Python không có giới hạn lưu trữ cho các kiểu dữ liệu trên.
- Ngoài 3 kiểu dữ liệu cơ bản trên, python còn có nhiều kiểu dữ liệu khác như `list`,`tuple`,... sẽ được tìm hiểu ở các bài sau.
- Các kiểu dữ liệu có thể được chuyển đổi qua lại cho nhau với các hàm sau:
	- `int()` chuyển về kiểu dữ liệu `int`
	- `float()` chuyển về kiểu dữ liệu `float`
	- `str()` chuyển về kiểu dữ liệu `string`
- Để khai báo một biến ta dùng cú pháp sau:
>[!code] Cú pháp khai báo biến
>```python
>tên biến = giá trị
>```

Ví dụ:
```python
number = 10
```

Tên biến tuân theo các quy tắc sau:
- Chỉ chứa chữ cái (`A-Z`,`a-z`), chữ số (`0-9`), dấu gạch dưới (`_`)
- Không được bắt đầu bằng chữ số
- Không trùng với các từ khóa, các tên định nghĩa sẵn

Tên biến _phân biệt chữ hoa chữ thường_, nên `Number`,`number` và `numBer` là 3 tên biến khác nhau
>[!caution] Lưu ý
>Khác với C/C++ và nhiều ngôn ngữ, ta _không_ đưa ra _kiểu dữ liệu_ của biến khi khai báo, kiểu dữ liệu sẽ được _xác định tự động_ qua dữ liệu


## Nhập xuất cơ bản:
- Để in nội dung ra màn hình, ta dùng hàm `print()`:

>[!code] Hàm `print()`
>```python
>print(xâu)
>```

Hàm `print()` nhận đối số kiểu xâu, là dãy các kí tự trong cặp dấu nháy đơn, ví dụ: `'hello'`
Đoạn trương trình dưới đây in ra dòng chữ "Hello world" trên màn hình:
```python
print('Hello world')
```
- Để nhập dữ liệu ta dùng hàm `input()`:

>[!code] Hàm `input()`
>```python
>input(lệnh nhắc)
>```

Khi thực thi hàm này, chương trình in ra `lệnh nhắc` và chờ người dùng nhập vào một nội dung, hàm `input()` sẽ trả về nội dung đó với kiểu dữ liệu xâu

Ví dụ:
```python
name = input('Enter your name: ')
```

Đầu tiên, chương trình sẽ in ra `Enter your name: ` và đợi người dùng nhập. Giả sử, người dùng nhập vào `Alex`, biến `name` sẽ có giá trị là `'Alex'`, kiểu `string`
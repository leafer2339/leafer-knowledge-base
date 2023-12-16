---
share: true
---

%%Tạo mới vào lúc 08:53:26 vào Ngày 20 tháng 06 năm 2023%%
#summer #programming 
13_Exceptions
Ngày 20 tháng 06 năm 2023 
08:53:30

# Bài 13: Xử lí lỗi và các ngoại lệ trong chương trình

## Lỗi trong Python
Trong Python có hai loại lỗi cơ bản:
- Lỗi cú pháp: xảy ra khi code không tuân thủ các cú pháp định nghĩa sẵn trong [The Python Language Reference](https://docs.python.org/3/reference/index.html) các lỗi này sẽ được chỉ ra trước khi chạy chương trình
```
  File "/home/luong/documents/coding/python/exception.py", line 1
    def divide(a,b)
                   ^
SyntaxError: expected ':'
```
Phía trên là một lỗi cú pháp, do ta không có dấu hai chấm (`:`) sau định nghĩa hàm
- Ngoại lệ (exception): những lỗi xảy ra khi chạy chương trình mặc dù cú pháp đúng. Một số lỗi có thể chỉ ra nhưng chuyển xâu không có chữ số sang số, hoặc truy cập vào phần tử không tồn tại trong [từ điển](./6_Dictionary.md), [danh sách](./4_Lists.md),... Những lỗi này sẽ hiển thị trong quá trình chạy chương trình
```
Traceback (most recent call last):
  File "/home/luong/documents/coding/python/exception.py", line 19, in <module>
    print(divide(7,0))
          ^^^^^^^^^^^
  File "/home/luong/documents/coding/python/exception.py", line 2, in divide
    return a/b
           ~^~
ZeroDivisionError: division by zero
```
Một ngoại lệ khi chạy chương trình: chia cho 0
Khi một ngoại lệ xảy ra, chương trình ngay lập tức sẽ dừng lại. Ta cần xử lí những ngoại lệ này để chương trình thực hiện thông suốt

## Xử lí ngoại lệ bằng cấu trúc `try...except`

>[!formula] Cấu trúc
>```python
>try:
>	<khối lệnh>
>{except <kiểu ngoại lệ> [ as <tên biến> ]:
>	<khối lệnh xử lí>}+
>```

Ví dụ như sau:

```python
try:
	n = int(input('Enter an odd number: '))
except ValueError as ve:
	print(ve)

```

Khi gặp cấu trúc này, khối lệnh trong `try` sẽ được thực hiện. Nếu khối lệnh thực hiện trơn tru sẽ thoát ra. Tuy nhiên, nếu gặp ngoại lệ, sẽ tra theo các khối `except` đến khi nhận được loại ngoại lệ tương ứng sẽ gán ngoại lệ đó cho biến (nếu có) rồi thực hiện khối lệnh trong `except`, rồi thoát ra ngoài. Trong trường hợp này ta sẽ in ra tin nhắn chi tiết lỗi xảy ra:

Ví dụ chạy chương trình:
```
$ python exception.py 
Enter an odd number: 123
$ python exception.py 
Enter an odd number: abc
invalid literal for int() with base 10: 'abc'
```

Ngoài ra, ta có khối `else` sẽ thực hiện nếu không có ngoại lệ nào được đưa ra. Trong ví dụ dưới dây, `divideEven()` sẽ đưa ra Exception nếu n âm hoặc là số lẻ
```python
try:
	n = int(input('Enter an even number: '))
	n2 = divideEven(n)
except ValueError as ve:
	print(ve)
except Exception as e:
	print('Error in divideEven(): {}'.format(e))
else:
	print(n2)

```
Chạy:
```
$ python exception.py 
Enter an even number: abc
invalid literal for int() with base 10: 'abc'
$ python exception.py 
Enter an even number: 123
Error in divideEven(): Odd value: 123
$ python exception.py 
Enter an even number: -10
Error in divideEven(): Negative value: -10
$ python exception.py 
Enter an even number: 8
4
```

Khối `finally` thực hiện cuối cùng trong mọi trường hợp, dù có tạo ra ngoại lệ hay không:
```
$ python exception.py 
Enter an even number: abc
invalid literal for int() with base 10: 'abc'
n = 0
$ python exception.py 
Enter an even number: 123
Error in divideEven(): Odd value: 123
n = 123
$ python exception.py 
Enter an even number: -124
Error in divideEven(): Negative value: -124
n = -124
$ python exception.py 
Enter an even number: 6
6 / 2 = 3
n = 6
```

## Ngoại lệ do người lập trình tạo
Ta có thể tự tạo ngoại lệ trong chương trình bằng từ khóa `raise`:

>[!formula] Cấu trúc tạo ngoại lệ
>```python
>raise <kiểu ngoại lệ>[ (<đối số>) ]
>```

Trong đó, <kiểu ngoại lệ> có thể là các [kiểu định nghĩa sẵn](https://docs.python.org/3/library/exceptions.html#bltin-exceptions) hoặc là một lớp do người dùng đặt kế thừa từ `Exception`.

Ví dụ, hàm `divideEven` được định nghĩa như sau:
```python
def divideEven(num):
	if num < 0:
		raise Exception('Negative value: {}'.format(num))
	if num % 2 == 1:
		raise Exception('Odd value: {}'.format(num))
	return int(num / 2)
```

Trong quá trình xử lí ngoại lệ, ta có thể đưa lại ngoại lệ ra ngoài bằng cách chỉ dùng từ khóa `raise`

%%Sửa đổi vào 09:22:29 Ngày 20 tháng 06 năm 2023%%
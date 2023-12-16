---
share: true
---

# Bài 3 Hàm
- Hàm là một mảnh chương trình. Một hàm thường có 3 phần:
	- Tên hàm
	- Danh sách tham số (có thể có hoặc không)
	- Thân hàm chứa các câu lệnh
## I. Định nghĩa hàm
Để định nghĩa hàm ta dùng cú pháp sau:
>[!code] Cú pháp định nghĩa hàm
>```python
>def <tên_hàm>([<danh sách tham số>]):
>	<khối lệnh thân hàm>

Ví dụ:
```python
def inc(i):
	return i+1
```

Trong ví dụ trên ta định nghĩa một hàm `inc` nhận tham số `i` và trả về kết quả `i+1`

>[!code] Câu lệnh return
>`return <giá trị>` kết thúc hàm và trả lại giá trị qua tên hàm


## II. Gọi hàm
- Để gọi hàm, ta dùng tên hàm và _truyền_ các đối số (argument) lần lượt cho các tham số

>[!code] Gọi hàm
>```python
><tên hàm>([<danh sách đối số tương ứng với các tham số>])
>```

Ví dụ, `inc(2)` sẽ gọi hàm `inc(i)` ở trên với `i = 2`

Khi đó, hàm `inc(2)` sẽ _trả về_ giá trị `i+1 = 3`:

```python
print(inc(2)) # 3
```

## III. Giá trị None
Nếu một hàm trong Python _không trả về bất cứ giá trị nào_, khi gọi hàm ta sẽ nhận được giá trị `None`

Ví dụ:

```python
def succ(i):
    return i+1

def write(i):
    print(i)

a = 2;
print(succ(2)) # 3
print(write(2)) # 2 None
```

## IV. Biến cục bộ và biến toàn cục
>[!notes] Định nghĩa
>- Biến _toàn cục_ (global variable) là các biến được định nghĩa và khai báo trong _chương trình chính_, nghĩa là toàn bộ chương trình python trong file `.py`
>- Biến _cục bọ_ (local variable) là các biến được định nghĩa và khai báo bên trong một _hàm_, một khối lệnh,...

Ví dụ:

```python
def write(i):
    print(i)

a = 2;
print(succ(2)) # 3
print(write(2)) # 2 None
```

Trong ví dụ trên `i` là biến được khai báo trên trong hàm `write`, nên `i` là biến cục bộ, còn `a` được khai báo trong chương trình, nên `a` là biến toàn cục.

- Khi một _biến toàn cục_ được khao báo bằng toán tử gán \-``python
>```python
>def succ(i):
>    return i+1
>
>def write(i):
>   print('i = ',i)
>   print('a = ',a)
>
>print(succ(2))
>print(write(2))
>a = 10;
>```
> Khi chạy ta nhận lỗi như sau:
> ```
> Traceback (most recent call last):
> File "/home/luong/documents/coding/python/func.py", line 9, in \<module\>
>     print(write(2))
>          ^^^^^^^^
>  File "/home/luong/documents/coding/python/func.py", line 6, in write
>    print('a = ',a)
>                 ^
>NameError: name 'a' is not defined
> ```

- Biến cục bộ chỉ có thể được sử dụng _bên trong thân hàm_. Ở bên ngoài không được phép dùng
Ví dụ:
```python
def succ(i):
    return i+1

def write(i):
    print('i = ',i)
    print('a = ',a)

a = 10;
print(succ(2))
print(write(2))
print(i) # NameError: name 'i' is not defined.
```

- Nếu ta muốn truy cập biến toàn cục bên trong hàm, ta cần dùng câu lệnh `global <tên biến>`:
```python
def succ(i):
    return i+1

def write(i):
    global a
    print(i) # 2
    a = 5
    print(a) # 5

a = 10
write(2)
print(a) # 5
```

Nếu ta không dùng câu lệnh `global`, việc thay đổi giá trị của biến toàn cục bằng phép gán sẽ tạo ra một biến cục bộ cùng tên:
```python
def succ(i):
    return i+1

def write(i):
    # global a
    print(i) # 2
    a = 5
    print(a) # 5

a = 10
write(2) 
print(a) # 10
```

## V. Đối số mặc định
Ta có thể đặt các _giá trị mặc định_ cho các tham số trong phần định nghĩa hàm. Nếu không có đối số nào được truyền cho tham số, các giá trị này sẽ được chọn
Đối số mặc định được định nghĩa bằng cách dùng cú pháp `<tên tham số> = <giá trị đối số mặc định>`

Ví dụ:
```python
def order(price, quantity = 1):
    print("you order " + str(quantity) + " objects, each costs " + str(price))
    return price * quantity

order(12,6) # you order 6 objects, each costs 12
order(40) #you order 1 objects, each costs 40
```
Trong lời gọi hàm thứ hai, `order(40)` ta không truyền giá trị nào cho tham số `quantity` nên tham số này lấy giá trị mặc định là `1`

>[!caution] Lưu ý
>Các tham số sử dụng đối số mặc định _bắc buộc_ phải được khai báo cuối
>Ví dụ:
>```python
>def order(price = 10, quantity):
>    print("you order " + str(quantity) + " objects, each costs " + str(price))
>    return price * quantity
>```
>
>Ta nhận được lỗi khi chạy:
>```
>  File "/home/luong/documents/coding/python/func.py", line 10
>    def order(price = 10, quantity):
>                          ^^^^^^^^
>SyntaxError: non-default argument follows default argument
>```

## VI. Truyền đối số
Có 2 kiểu truyền đối số trong Python:
- Truyền theo _vị trí_ (**positional argument**), đối số được truyền vào tham số theo thứ tự tham số, ví dụ:

```python
def lprint(para1, para2, para3):
	print(f'para1: {para1}, para2: {para2}, para3: {para3}')

lprint(1,2,3) # para1: 1, para2: 2, para3: 3
```
- Truyền theo _từ khóa_  (**keyword argument**), đối số được truyền bằng cách gán trực tiếp tham số với giá trị trong phép gọi hàm:
```python
def lprint(para1, para2, para3):
	print(f'para1: {para1}, para2: {para2}, para3: {para3}')

lprint(para1=1,para2=2,para3=3) # para1: 1, para2: 2, para3: 3
```
- Ta có thể kết hợp hai kiểu truyền đối số với nhau, tuy nhiên phải tuân theo các quy tắc như:
	- Các đối số truyền theo vị trí **bắt buộc** phải đặt trước các đối số truyền theo từ khóa
	- Một tham số không thể lấy **hai đối số**

Để thuận tiện, khi định nghĩa hàm, ta có thể chỉ ra các tham số được truyền theo vị trí hay từ khóa với cấu trúc dưới đây:

>[!code] Cấu trúc khai báo hàm cùng cách truyền đối số
>```
>def <tên hàm>(<danh sách đối số chỉ truyền theo vị trí> , / , <danh sách đối số có thể truyền theo vị trí hoặc từ khóa , * ,  <danh sách đối số chỉ truyền theo từ khóa>)
>```

Ví dụ:
```python
def func(pos1, pos2, /, poskey1, poskey2, *, key1, key2):
    print("pass with position pos1: \'" + str(pos1) + "\' pos2: \'" + str(pos2) + "\'")
    print("pass with position or keyword poskey1: \'" + str(poskey1) + "\' poskey2: \'" + str(poskey2) + "\'")
    print("pass with keyword key1: \'" + str(key1) + "\' pos2: \'" + str(key2) + "\'")

func(1,2,3,poskey2=4,key1=5,key2=6)
# pass with position pos1: '1' pos2: '2'
# pass with position or keyword poskey1: '3' poskey2: '4'
# pass with keyword key1: '5' pos2: '6'
```


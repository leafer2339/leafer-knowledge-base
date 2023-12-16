---
share: true
---

%%Tạo mới vào lúc 20:42:46 vào Ngày 20 tháng 06 năm 2023%%
#summer #programming 
14_Class
Ngày 20 tháng 06 năm 2023 
20:42:51

# Bài 14: Lớp
**Lớp (class)** là một cách để gộp, nhóm dữ liệu, hàm lại với nhau, tạo thành một kiểu dữ liệu do người dùng để tạo ra các **đối tượng (object)**

## Định nghĩa lớp

>[!formula] Cú pháp định nghĩa lớp
>```python
>class <tên lớp>:
>	<các biến và hàm tại đây>
>```

Ví dụ:
```python
class C:
	x = 1
	def one():
		return 1
```

Ví dụ trên tạo ra một lớp C. `x` và `one()` là các thuộc tính lớp, có thể được truy cập qua toán tử `.`:

```python
print(C.x) # 1
print(C.one()) # 1
```

Tất cả những biến, hàm,... được định nghĩa trong lớp đều có thể được truy cập theo cách như vậy. 
Để tạo một đối tượng thuộc lớp C, ta gọi lớp C như một hàm:

```python
a = C()
```

Biến a giờ đây là một đối tượng thuộc lớp `C`. 

## Làm việc với đối tượng
Một đối tượng có toàn quyền truy cập các biến thuộc lớp, ví dụ:

```python
print(a.x) # 1
```

Các thuộc tính của đối tượng, cũng như mọi định danh khác trong python, _chỉ xuất hiện khi được gán_

Ta có thể tạo các thuộc tính của đối tượng mà không liên quan đến thuộc tính lớp:
```python
a.b = 2 
print(a.b) # 2
print(C.b) # AttributeError: type object 'C' has no attribute 'b'
```
Như vậy, các thuộc tính được định nghĩa trong định nghĩa lớp sẽ đóng vai trò tương đương như các **static member (thành phần tĩnh)** của lớp trong C++. 

Các phương thức lại có cách hoạt động tương đối khác. Khi ta gọi `a.func(...)`, thực chất ta đang gọi `C.func(a,...)` Tức là, khi gọi phương thức, đối tượng sẽ được truyền như một đối số trong hàm thuộc lớp.

Như vậy các phương thức có thể gọi được bởi đối tượng cần _ít nhất 1_ tham số, thường được gọi là `self`, chỉ đối tượng đang gọi phương thức, ví dụ:
```python
class C:
	x = 1
	def one():
		return 1
	def setValue(self,value):
		self.value = value
```

Khi  đó các đối tượng thuộc lớp `C` có thể gọi `setValue`:
```python
a = C()
a.setValue(10)
print(a.value) # 10
```

## Các phương thức đặc biệt
`__init__` là phương thức được gọi khi lớp được dùng để tạo một đối tượng mới, tương tự như hàm khởi tạo (constructor) trong C++:
```python
class Person:
	species = 'human'
	def __init__(self,name='',money=0):
		self.name = name
		self.money = money
```

```python
luong = Person('luong',100000)
print("Name: {}, Money: {}".format(luong.name,luong.money))
# Name: luong, Money: 100000
```

%%Sửa đổi vào 08:50:30 Ngày 22 tháng 06 năm 2023%%

## Kế thừa
Kế thừa là một tính chất đặc biệt, cho phép lớp này (Lớp con, lớp được kế thừa) sao chép những thuộc tính, phương thức từ lớp khác (lớp mẹ, lớp kế thừa) nhằm tránh lặp code.

Để định nghĩa một lớp kế thừa các thuộc tính, phương thức của lớp khác ta dùng: 

```python
class Derived(Base):
```

Ngoài ra một lớp có thể kế thừa từ nhiều lớp khác nhau. Sau khi kế thừa ta có thể toàn quyền dùng, thậm chí là cả sửa đổi phương thức của lớp mẹ, nếu ta muốn dùng lại phương thức của lớp mẹ ta có thể dùng `<tên lớp mẹ>.<phương thức>([<đối số>])`
```python
class Base:
	def __init__(self):
		self.a = 1
		self.b = 2
	def inc(self):
		self.a += 1
		self.b += 2
	def Print(self):
		print('Base: a: {}, b: {} '.format(self.a,self.b))

class Derived(Base):
	def __init__(self):
		Base.__init__(self)
		self.c = 5
	def incC(self):
		self.c += 5
	def inc(self):
		Base.inc(self)
		self.incC()
	def Print(self):
		print('Derived: a: {}, b: {}, c: {} '.format(self.a,self.b,self.c))

```
(Một ví dụ về kế thừa)
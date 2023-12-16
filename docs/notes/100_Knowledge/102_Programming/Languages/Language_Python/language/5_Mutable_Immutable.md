---
share: true
---

#summer #programming #lang/py 
# Bài 5 Khả năng thay đổi dữ liệu. Kiểu dữ liệu bộ (tuple)

## I. Tham chiếu.
- Khi ta định nghĩa một [biến](./1_Basics.md) trong python, ví dụ:
```python
a = 1
```
- Khi đó, python tạo ra một vùng nhớ chứa giá trị 1. Biến a chứa **tham chiếu (reference)** đến vùng nhớ đó. Để biết được tham chiếu này, ta dùng hàm `id()`:
```python
a = 1
print(id(a)) # 140305669485544
```
- Khi ta thay đổi giá trị biến a, ví dụ:
```python
a = 2
```
- Python lúc này tạo một vùng nhớ khác có giá trị 2 và gán tham chiếu đến nó vào giá trị a, khi dùng hàm `id()` ta thấy giá trị thay đổi:
```python
a = 1
print(id(a)) # 140164805882856
a = 2
print(id(a)) # 140164805882888
```
- Phép gán thực chất chỉ chuyển tham chiếu từ biến gán cho biến được gán:
```python
a = 1
print(id(a)) # 139685252232168
b = a
print(id(b)) # 139685252232168
```

## II. Hai loại kiểu dữ liệu: Mutable và Immutable

- Như vậy, với biến a ở trên, cụ thể là kiểu số nguyên `int`, khi thay đổi giá trị ta sẽ thay đổi chính biến đó. Biến này không cho phép trực tiếp thay đổi giá trị của nó. Kiểu dữ liệu `int` được gọi là **immutable**.
- Để minh họa rõ hơn, `string` cũng là một kiểu dữ liệu immutable. Việc thay đổi giá trị của xâu (không qua phép gán giá trị mới) là không được phép:
```python
s = 'hello'
s[1] = 'a' # TypeError: 'str' object does not support item assignment
```
Xâu cũng là một dãy các kí tự, giống như [danh sách](./4_Lists.md), nhưng mặc dù ta có thể trực tiếp thay đổi phần tử của danh sách, ta không thể làm vậy với xâu. Để thay đổi ta phải lấy xâu con và dùng phép ghép xâu, khi đó biến chứa xâu sẽ tham chiếu đến vùng nhớ khác:
```python
s = 'hello'
print(id(s)) # 140504226332528
s = s[0] + 'a' + s[2:]
print(s) # hallo
print(id(s)) # 140504224064432
```

>[!notes] Định nghĩa
>Kiểu dữ liệu immutable là các kiểu dữ liệu không cho phép thay đổi dữ liệu đang giữ qua tham chiếu.


- Ngược lại với immutable ta có kiểu dữ liệu **mutable**. Về cơ bản, kiểu dữ liệu này cho phép thay đổi dữ liệu qua tham chiếu. Ví dụ đổi với danh sách ta có các phương thức như `insert()`,`append()` thay đổi trực tiếp giá trị của danh sách mà không làm thay đổi tham chiếu:
```python
a = [1,2,3]
print(id(a)) # 139927566118912
a.append(4)
print(id(a)) # 139927566118912
```
- Tuy nhiên, nếu ta gán một danh sách cho một danh sách hoàn toàn mới, tham chiếu sẽ thay đổi do phép gán.

>[!notes] Định nghĩa
>Kiểu dữ liệu mutable là các kiểu dữ liệu cho phép thay đổi giữ liệu đang giữ qua tham chiếu

- Xét ví dụ sau:
```python
stra = 'hello'
strb = stra

lista = [1,2,3]
listb = lista
```

Đối với kiểu `string`, vì là immutable, nên cho dù `strb` và `stra` cùng tham chiếu đến một vùng nhớ, khi ta thay đổi một trong hai biến, biến bị thay đổi sẽ tham chiếu đến vùng nhớ mới, biến còn lại giữ nguyên giá trị:
```python
strb = 'goodbyte'
print(stra) # hello
print(strb) # goodbyte
```
Đối với `list`, vì là mutable, khi ta thay đổi `stra` hoặc `strb`, ta thay đổi vùng nhớ chúng cùng tham chiếu đến:
```python
lista = [1,2,3]
listb = lista
listb[1] = 4
printList(lista) # 1 4 3
printList(listb) # 1 4 3
```

- Khi ta truyền đối số cho [hàm](./3_Functions.md), việc ta làm là gán các tham số cho đối số. Như vậy ta có thể chỉnh sửa các tham số là kiểu dữ liệu mutable được truyền vào hàm, mà không thể làm điều tương tự với các biến thuộc kiểu dữ liệu immutable:

```python

def printList(l):
	print('[',end='')
	for i in l:
		print(i,end=',')
	print(']')


def changeInt(a):
	a = 5
	print('a= ',a) # a = 5

def changeList(a):
	a[0] = 5
	print('a = ')
	printList(a) # a = [5,2,3]

num = 10
l = [1,2,3]

changeInt(num)
print('num = ',num) # num = 10
changeList(l)
print('l = ') 
printList(l) # l = [5,2,3,]
```

## 3. Kiểu dữ liệu tuple
- **Tuple (bộ)** cũng là một tập hợp các dữ liệu, giống như [danh sách](./4_Lists.md), tuy nhiên, các dữ liệu trong tuple được đặt giữa dấu ngoặc đơn `()` và tuple là một kiểu dữ liệu immutable.
- Để tạo ra một biến tuple ta làm như ví dụ sau:
```python
a = (1,2,3)
```
- Vì là immutable, ta chỉ có thể truy cập đến phần tử của tuple chỉ với mục đích đọc, và tuple bị hạn chế các thao tác và phương thức, chỉ còn `index()` và `count()` là giống với list. 
- Ta có thể chuyển đổi qua lại giữa list và tuple với hai hàm `list()` và `tuple()`


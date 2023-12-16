---
share: true
---

#summer #programming #lang/py 
# Bài 4 Kiểu dữ liệu danh sách (lists)
# I. Tổng quan về list
- **Danh sách (list)** là một _dãy_ các giá trị, có thể cùng hoặc khác loại, nhưng thường là cùng kiểu dữ liệu
- Một danh sách trong python được đặt giữa hai dấu ngoặc vuông `[]`, ví dụ:
```python
a = [1,2,3] # mảng gồm 3 phần tử số nguyên
b = [4,5.2, 'hello'] # mảng gồm các phần tử khác kiểu dữ liệu
```
- Để truy cập phần tử trong mảng, ta dùng cú pháp
>[!code] Cú pháp phần tử mảng
>```python
><tên mảng>[<số chỉ vị trí>]
>```

- Do danh sách là một kiểu dữ liệu **mutable**, việc truy cập cho phép ta _chỉnh sửa_ phần tử bên trong mảng

Trong đó, <số chỉ vị trí> _bắt buộc là số nguyên_. Ví dụ, với mảng a, `a[0]`, `a[1]` là các các truy cập hợp lệ, còn `a[0.1]` là không hợp lệ, sẽ trả về `TypeError`
- Đối với python, ta có thể dùng _số chỉ vị trí âm_. Ví dụ: `a[-1]` sẽ cho kết quả giống với `a[n-1]`, với n là số phần tử mảng.
- Như vậy, `<số chỉ vị trí>` có khoảng giá trị cho phép là từ `-n` đến `n-1`, với n là chiều dài của mảng
Ví dụ:
```python
a = [1,2,3]
b = [1,2,'hello']

print(a[0]) # 1
print(b[-1]) # hello
print(a[5]) # TypeError
print(b[-4]) # TypeError
```
- Ta có thể tạo ra một danh sách con từ danh sách ban đầu với cú pháp sau:
>[!code] Tạo danh sách con từ phần tử thứ i đến phần tử thứ j-1
>```python
><tên mảng>[i:j]
>```

- i và j có thể là số âm, nhưng phải trong phạm vi truy cập của mảng
- Nếu khuyết i, ta sẽ lấy từ đầu mảng, tức i = 0
- Nếu khuyết j, ta sẽ lấy đến cuối mảng, tức j = n (n là chiều dài của mảng)
Ví dụ:
```python

def printList(l):
	for item in l:
		print(item,end=' ')
	print()

printList(a)
printList(a[2:5]) # 3 4 5
printList(a[-6:-2])# 5 6 7 8
printList(a[:3]) # 1 2 3
printList(a[6:]) # 7 8 9 10
printList(a[:]) # 1 2 3 4 5 6 7 8 9 10
```

# II. Các hàm và phương thức liên quan đến danh sách
- Hàm `len()` trả về _độ dài_ của danh sách:
```python
a = [1,2,3,4,5,6,7,8,9,10]
print(len(a)) # 10
```
- Toán tử `in` và `not in` kiểm tra xem liệu một phần tử có nằm trong danh sách hay không:
```python
a = [1,2,3,4,5,6,7,8,9,10]
print(5 in a) # True
print(20 in a) # False
print(7 not in a) # False
print(100 not in a) # True
```
- Câu lệnh `del <tên danh sách>[<số chỉ vị trí>]` sẽ xóa phần tử ở vị trí đó khỏi danh sách:
```python
a = [1,2,3,4,5,6,7,8,9,10]
del a[5]
printList(a) # 1 2 3 4 5 7 8 9 10
```
- Danh sách có thể được nối với nhau dùng toán tử `+`. Ngoài ra, danh sách cũng có thể được nhân lên nhiều lần với toán tử `*`
```python
a = ['a',1,2,3,4,5,6,7,8,9,10]  
b = ['b',11,12,13,14,15]
printList(a+b) #a 1 2 3 4 5 6 7 8 9 10 b 11 12 13 14 15 
printList(a*2) #a 1 2 3 4 5 6 7 8 9 10 a 1 2 3 4 5 6 7 8 9 10 
```
- Hàm `enumerate()` nhận một dãy và trả về dãy các cặp giá trị, với giá trị đầu tiên là một số, biểu thị vị trí của phần tử đang xét, giá trị thứ hai là phần tử đang xét trong danh sách, ví dụ:
```python
for index, value in enumerate(a):
	print('a['+str(index)+'] = '+str(value))
``` 
Kết quả:
```
a[0] = a
a[1] = 1
a[2] = 2
a[3] = 3
a[4] = 4
a[5] = 5
a[6] = 6
a[7] = 7
a[8] = 8
a[9] = 9
a[10] = 10
``` 
- Phương thức `index(x)` trả về vị trí xuất hiện đầu tiên của giá trị `x` trong danh sách. Nếu không có giá trị báo lỗi `ValueError`
```python
a = ['Peculiar','Serendipity','Resilient','Epiphany','Wistful','Ineffable','Mellifluous','Quixotic','Ephemeral','Ubiquitous','Epiphany']
print(a.index('Epiphany')) # 3
print(a.index('Science')) # ValueError 
```
- Phương thức `append(x)` thêm giá trị x vào _cuối_ danh sách:
- Phương thức `insert(i,x)` thêm giá trị `x` vào vị trí `i` trong danh sách. Sau phép gọi `l.insert(i,x)`, với $-len(x)\le i \le len(x)$ `l[i] = x` . Nếu $i < -len(x)$, i sẽ lấy giá trị là $-len(x)$, còn nếu $i > len(x)$, i sẽ lấy giá trị $len(x)$
Ví dụ:

```python
a = [1,2,3,4,5,6,7,8,9,10]
a.append(11)
printList(a) # 1 2 3 4 5 6 7 8 9 10 11 
a.insert(3,12)
printList(a) # 1 2 3 12 4 5 6 7 8 9 10 11 
a.insert(15,13)
printList(a) # 1 2 3 12 4 5 6 7 8 9 10 11 13 
a.insert(-20,14)
printList(a) # 14 1 2 3 12 4 5 6 7 8 9 10 11 13
```
- Phương thức `remove(x)` loại bỏ giá trị `x` khỏi danh sách. Nếu giá trị `x` không nằm trong danh sách sẽ xuất hiện ValueError. Nếu `x` xuất hiện nhiều lần trong danh sách, xóa lần xuất hiện đầu tiên của `x`
Ví dụ
```python
a = [1,2,3,4,5,6,7,8,9,10]
a.remove(7)  # 1 2 3 4 5 6 8 9 10 
printList(a)
a.remove(12) # ValueError
printList(a)
```
- Phương thức `sort()` sắp xếp các phần tử trong danh sách theo thứ tự tăng dần. Một số tham số tùy chọn:
	- `reverse`: nếu gán bằng `True`, sẽ sắp xếp danh sách theo thứ tự giảm dần
	- `key`: một hàm biểu thị cách sắp xếp phần tử (sẽ đề cập ở phần sau)

Ví dụ:
```python
a = [43, 79, 18, 91, 7, 64, 27]
a.sort()
printList(a) # 7 18 27 43 64 79 91 
```
```python
a = [43, 79, 18, 91, 7, 64, 27]
a.sort(reverse=True)
printList(a) # 91 79 64 43 27 18 7  
```

- Phương thức `reverse()` đảo ngược vị trí các phần tử của mảng:
```python
a = [43, 79, 18, 91, 7, 64, 27]
a.reverse();
printList(a); # 27 64 7 91 18 79 43
```

- Ta có thể gán các phần tử của danh sách lần lượt cho nhiều biến với cú pháp:
```
<danh sách biến, phân cách bởi dấu phẩy> = danh sách
```
Lưu ý: số lượng biến được gán giá trị phải _bằng đúng_ số lượng phần tử trong danh sách. Nếu nhiều hơn hay ít hơn sẽ tạo `ValueError`

```python
a = [43, 79, 18, 91, 7, 64, 27]
var1,var2,var3,var4,var5,var6,var7 = a
print(var1,var2,var3,var4,var5,var6,var7,sep=',') # 43,79,18,91,7,64,27
```


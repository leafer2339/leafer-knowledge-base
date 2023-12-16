---
categories:
  - python-language
share: true
---

#summer #programming #lang/py 
# Bài 6 Kiểu dữ liệu từ điển (dictionary)

- **Từ điển (dictionary)** là một loại kiểu dữ liệu ghép (mapping). Từ điển về cơ bản là một danh sách các cặp khóa-giá trị (key-value).
- Từ điển thuộc loại kiểu dữ liệu mutable.
- Key (khóa) có thể thuộc hầu hết các kiểu dữ liệu, trong khi các kiểu dữ liệu [mutable](./5_Mutable_Immutable.md) không thể được dùng cho value.

## 1. Khởi tạo từ điển
- Cách thông thường là dùng các cặp khóa-giá trị dưới cú pháp : `<khóa> : <giá trị>`, đặt trong cặp dấu ngoặc nhọn `{}`, phân cách bởi dấu phẩy, ví dụ:
```python
inventory = { 'torch' : 15, 'dirt' : 64, 'stick' : 20  }
```
- Cách thứ hai qua phương thức khởi tạo `dict()`, nhận một danh sách các cặp `(<khóa>,<giá trị>)`:
```python
inventory = dict([('torch',15),('dirt',64),('stick',20)])
```

## 2. Truy cập phần tử của từ điển
- Để truy cập một giá trị của từ điển, ta cần cung cấp khóa của nó qua toán tử truy xuất `[]` với cú pháp
```
<tên từ điển>[<khóa]
```
- Nếu `<khóa>` không nằm trong từ điển sẽ đưa ra `KeyError`. Tuy nhiên ta có thể dùng phép gán để nhanh chóng thêm phần tử mới vào từ điển.
- Vì là mutable, qua việc truy xuất này ta cũng có thể thay đổi giá trị mà khóa đó đang giữ
- Ví dụ:
```python
print(inventory['torch']) # 15
print(inventory['grass']) # KeyError
```
- Ngoài ra, từ điển cung cấp phương thức `get(<khóa>[,<giá trị>])` với tham số tùy chọn `<giá trị>` cho phép ta cung cấp giá trị trả về nếu `<khóa>` không nằm trong từ điển

```python
print(inventory.get('torch',0)) # 15
print(inventory.get('grass',0)) # 0
```
- Ngược lại với phương thức `get()`, ta có phương thức `setdefault(<khóa>[,<default>])`. Nếu `<khóa>` nằm trong từ điển, phương thức này trả về giá trị, ngược lại, tạo giá trị `<default>` với khóa đã cho

```python
inventory.setdefault('shovel',2)
print(inventory['shovel']) # 2
```

- Các phương thức `keys()`, `values()` và `items()` lần lượt trả về danh sách gồm khóa, giá trị và cặp trên trong từ điển:

```python
for i in inventory.keys():
	print(i,end=' ')
print() # torch dirt stick shovel 
for i in inventory.values():
	print(i,end=' ')
print() # 15 64 20 2 
for i in inventory.items():
	print(i,end=' ')
print() # ('torch', 15) ('dirt', 64) ('stick', 20) ('shovel', 2) 
```

- Phương thức `update()` được dùng để nhập 2 từ điển với nhau:
```python
things = {'a':1,'b':2}
other  = {'c':3,'d':4}
things.update(other)

print(things) # {'a': 1, 'b': 2, 'c': 3, 'd': 4}
```
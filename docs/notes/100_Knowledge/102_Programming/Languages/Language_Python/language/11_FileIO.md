---
share: true
---

#summer #programming 
11_FileIO
Ngày 17 tháng 06 năm 2023 
10:01:46

# Bài 11: Nhập xuất với tệp
## Tổng quan:
Làm việc với tệp có thể chia thành 3 phần chính:
- Mở tệp
- Đọc/ghi tệp
- Đóng tệp để lưu dữ liệu
Trong python, ta có các đối tượng tệp (file object) để giúp làm việc với tệp.
## Thao tác với tệp dùng các phương thức có sẵn
### Mở tệp
- Để mở tệp ta dùng hàm `open()`:
```
open(mode='r',buffering=-1,...)
```
Một số tham số:
- `mode`: chế độ mở file, đầu tiên là 'r','w','a' hoặc 'x':

|mode|ý nghĩa|
|---|---|
|r|đọc file, báo lỗi nếu file không tồn tại|
|w|ghi file, nếu file tồn tại sẽ bị xóa sạch, nếu không tồn tại sẽ được tạo mới|
|a|ghi file từ cuối file|
|x|tạo file|

Sau đó có thể có dấu '+', biểu thị sẽ cả đọc và ghi file.
Cuối cùng là 't' (mặc định) hoặc 'b' biểu thị file là văn bản hay nhị phân
- buffering: bộ lớn vùng đệm trong việc đọc file
- newline: kí tự dòng mới (xem thêm trong phần đọc file ở dưới)
- encoding và error: tùy chọn của việc mã hóa file

Các file được sử dụng:

### Đọc file

- `read(size)` đọc một lượng dữ liệu từ tệp và trả về. Nếu `size` không được đưa ra hoặc âm sẽ đọc toàn bộ file.
```python
f = open('./thamquan.INP',mode='r+',buffering=5,newline='\n')
print('|{}|'.format(f.read(3))) # |4 6|
```
- `readline()` đọc một dòng từ tệp:
```python
f = open('./thamquan.INP',mode='r+',buffering=5)
print('|{}|'.format(repr(f.readline()))) # |'4 6\n'|
```
Tham số `newline`(chỉ dành cho chế độ `t`) sẽ ảnh hưởng đến phương thức này.
- Nếu `newline` là None (mặc định), dòng đọc kết thúc bằng `\r`,`\n`,`\r\n`và khi trả về dòng sẽ kết thúc bằng `\n`:
- Nếu `newline = ''`, tương tự như trên nhưng các kí tự dòng mới được giữ nguyên, trong trường hợp của file `thamquan.INP`, mỗi dòng kết thúc bằng `\r\n`:
```python
f = open('./thamquan.INP',mode='r+',buffering=5,newline='')
print('|{}|'.format(repr(f.readline()))) # |'4 6\r\n'|
```
- Còn lại, `newline` có các giá trị: `\r`,`\n` hoặc `\r\n` sẽ đọc đến kí tự này và trả nguyên về, sau đó tiếp tục đọc từ kí tự tiếp theo:
```python
f = open('./thamquan.INP',mode='r+',buffering=5,newline='\r')
print('|{}|'.format(repr(f.readline()))) # |'4 6\r'|
print('|{}|'.format(repr(f.readline()))) # |'\n3  13  4  6\r'|
print('|{}|'.format(repr(f.readline()))) # |'\n34 23 28 22 32 30'|
```
- `readlines()` trả về một danh sách các dòng của file:
```python
thamquan = open('./thamquan.INP',mode='r+',buffering=5,newline='\r')
print(thamquan.readlines()) # ['4 6\r', '\n3  13  4  6\r', '\n34 23 28 22 32 30']
```
Ngoài ra ta có thể chuyển tệp thành [danh sách](./4_Lists.md) bằng hàm `list()`:
```python
print(list(thamquan)) # ['4 6\r', '\n3  13  4  6\r', '\n34 23 28 22 32 30']
```

### Vị trí hiện tại của file
Sau khi đọc file, một "con trỏ" vô hình chứa vị trí của file sẽ di chuyển, hàm đọc sau sẽ bắt đầu từ vị trí này. Phương thức `tell()` cho biết vị trí này:
```python
print(thamquan.read(4)) # 4 6 , đọc 4 kí tự, hiện ở kí tự 4 (bắt đầu đánh số từ 0)
print(thamquan.tell()) # 4
```
Để chuyển vị trí này ta dùng phương thức `seek(offset, whence)` tiến `offset` vị trí từ vị trí `whence`
Bảng giá trị `whence:`

|whence|vị trí|
|---|---|
|0|đầu file|
|1|vị trí hiện tại (chỉ dành cho nhị phân)|
|2|cuối file (chỉ dành cho nhị phân|

Ví dụ:
```python
thamquan = open('./thamquan.INP',mode='r+b',buffering=5)
print(thamquan.read(1)) # b'4'
thamquan.seek(3,0)
print(thamquan.read(1)) # b'\r'
thamquan.seek(4,1)
print(thamquan.read(1)) # b'1'
thamquan.seek(-5,2)
print(thamquan.read(1)) # b'3'
```

### Ghi file
`write()` viết một đoạn văn bản/bộ đệm vào file:
```python
thamquan = open('./data.txt',mode='w',buffering=5)
thamquan.write('python')
```
Sau khi chạy tệp `data.txt` như sau:
```
python
```
`writelines()` ghi lần lượt các phần tử của một danh sách vào file:
```python
thamquan = open('./data.txt',mode='w',buffering=5)
text = ['bai 11\n','nhap xuat file\n']
thamquan.writelines(text)
```
Sau khi chạy
```
bai 11
nhap xuat file
```

%%Tạo mới vào lúc 10:01:41 vào Ngày 17 tháng 06 năm 2023%%
%%Sửa đổi vào 09:55:16 Ngày 18 tháng 06 năm 2023%%
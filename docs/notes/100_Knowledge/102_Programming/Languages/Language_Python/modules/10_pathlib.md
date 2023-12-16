---
share: true
---

#summer #programming 
10_pathlib
Ngày 15 tháng 06 năm 2023 
14:09:22

# Bài 10 Sử dụng module `pathlib` để làm việc với file

Xem thêm tại: [pathlib](https://docs.python.org/3/library/pathlib.html)

## Tệp, thư mục và đường dẫn
Cấu trúc lưu trữ tệp (file) trên các hệ điều hành gồm nhiều **thư mục**, mỗi thư mục gồm các thư mục con và các tệp.

![file.excalidraw](file.excalidraw.md)

**Đường dẫn** đến một tệp liệt kê tất cả các thư mục cần thiết để chạm tới tệp đó, từ một thư mục gốc. Trong trường hợp này là thư mục **root(/)**. Trong ví dụ trên, đường dẫn đến tệp `hello.md` là `/home/luong/documents/hello.md`

- Đối với Linux và macOS, các thư mục trong đường dẫn được phân cách bởi kí hiệu `/`, còn trong Windows lại là `\`. Để dễ dàng thực hiện các thao tác với tệp, module `pathlib` cung cấp lớp `Path`. Để sử dụng ta cần :
```python
from pathlib import Path
```

## Tạo `Path` chỉ đến đường dẫn
- Ta có thể dùng phương thức khởi tạo `Path()` để tạo một đường dẫn mới sử dụng trong chương trình. Phương thức này nhận các tham số xâu, kết hợp với nhau tạo thành một đường dẫn, ví dụ:
```python
f = Path('/','home','luong','documents')
```
Biến `f` chứa đường dẫn chỉ tới thư mục `/home/luong/documents`. Ta nhận được đường dẫn khi chuyển biến này về kiểu xâu rồi in ra:
```python
print(str(f)) # /home/luong/documents
```
Ngoài ra, kiểu của biến `f` sẽ phục thuộc vào hệ điều hành đang sử dụng. Trên Linux `f` thuộc kiểu `PosixPath` còn trên Windows `f` thuộc kiểu `WindowsPath`. 


Toán tử này thực hiện _từ trái sang phải_, nên nếu sử dụng trên nhiều dữ liệu, cần chắc chắn một trong hai dữ liệu đầu tiên là một đối tượng kiểu `Path`

## Làm việc với `Path`
### Đường dẫn thuần
- `PurePath` (tạm dịch: đường dẫn thuần) là lớp cung cấp các phương thức làm việc với đường dẫn _mà không cần can thiệp vào hệ thống file (filesystem)_. Nói cách khác, các lớp này chỉ làm việc với đường dẫn tương tự như làm việc với xâu. Dựa theo hệ điều hành chia thành 2 lớp:
	- PosixPurePath dùng cho các hệ điều hành thuộc họ Unix như Linux hay macOS
	- WindowsPurePath dùng cho các hệ điều hành Windows
- Các đường dẫn thuộc kiểu dữ liệu [immutable](../language/5_Mutable_Immutable.md)
#### Nối đường dẫn
- Khi có một biến kiểu `Path`, ta có thể dùng toán tử `/` để kết nối tên thư mục/tệp vào với nhau, mở rộng đường dẫn, tương tự như toán tử `+`  được dùng để ghép xâu:
```python
book = f/'books'
print(book) # /home/luong/documents/books
```
#### Thuộc tính
`parts` là một [tuple](../language/5_Mutable_Immutable.md#3.%20Kiểu%20dữ%20liệu%20tuple) liệt kê từng phần của đường dẫn
```python
f = Path('/','home','luong','documents')
book = f/'books'
print(book.parts) # ('/', 'home', 'luong', 'documents', 'books')
```
- `drive`: lấy tên ổ đĩa (Windows):
- `root`: lấy tên thư mục gốc
- `anchor`: kết hợp của `drive()` và `root()`:
Ví dụ:
```python
print(book.drive) # (empty)
print(book.root) # /
print(book.anchor) # /
```
- `parents`: một [danh sách](../language/4_Lists.md) immutable chứa thư mục mẹ của đường dẫn:
```python
for p in book.parents:
	print(p)
#/home/luong/documents
#/home/luong
#/home
#/
```
- `parent`: giống `parents[0]`, trả về thư mục mẹ đầu tiên ngay trước đường dẫn
- `name`: tên của thư mục/tệp đường dẫn chỉ đến:
```python
print(book.name) # books
```
- `suffix`: phần mở rộng cuối cùng của tệp, nếu tệp có nhiều phần mở rộng, `suffixes` trả về tất cả phần mở rộng 
```python
print(book.suffix) # .gz
print(book.suffixes) # ['.tar','.gz']
```
- `stem`: tên file không có phần mở rộng cuối cùng:
```python
print(book.stem) # sth.tar
```
#### Phương thức
- **Đường dẫn tuyệt đối (absolute path)** là đường dẫn đến thư mục/tệp _từ thư mục root_
- **Đường dẫn tương đối (relative path)** là đường dẫn đến thư mục/tệp _từ thư mục hiện hoạt (cwd)_
Ví dụ 
`/home/luong/documents/coding/python/files/data.txt` là đường dẫn tuyệt đối
`./data.txt` là đường dẫn tương đối, với cwd là `/home/luong/documents/coding/python/files`
- Phương thức `is_absolute()` kiểm tra một đường dẫn có phải đường dẫn tuyệt đối hay không:
```python
print(book.is_absolute()) # True
cpf = Path('coding','python','file')
print(cpf.is_absolute()) # False
```
- Phương thức `is_relative_to()` kiểm tra một đường dẫn có tương đối với một đường dẫn khác hay không:
```python
print(cpf.is_relative_to('coding')) # True
```
%% Sửa đổi vào 08:36:58 Ngày 17 tháng 06 năm 2023 %%
- Phương thức `match()` kiểm tra một đường dẫn có phù hợp với một [quy luật kiểu glob](https://en.wikipedia.org/wiki/Glob_(programming)) hay không, ví dụ:

```python
print(book.match(r'*.tar.gz')) # True
print(book.match(r'/home/luong/documents/books/*')) # True 
print(book.match(r'/home/luong/documents/paper/*')) # False
```
### Đường dẫn hệ thống (Concrete Paths)
- `Path` cho phép làm việc với đường dẫn _có truy cập đến filesystem_, chia làm hai loại phụ thuộc vào hệ điều hành:
	- `WindowsPath` dành cho các hệ điều hành Windows
	- `PosixPath` dành cho các hệ điều hành Unix
#### Các Phương thức lớp:
- `cwd()`: Thư mục làm việc (current working directory - cwd) chỉ thư mục chương trình hiện tại đang làm việc bên trong (thường là thư mục chứa tệp chạy chương trình). Để lấy được thư mục này ta sử dụng phương thức `cwd()`:
```python
print(Path.cwd()) # /home/luong/documents/coding/python/files
```
- `home()`: Đối với mỗi hệ điều hành, mỗi người dùng được cấp một thư mục riêng để làm việc, gọi là thư mục `home`. Phương thức `home()` trả về thư mục này:
```python
print(Path.home()) # /home/luong
```
#### Phương thức đối tượng
- Có 3 phương thức cơ bản để kiểm tra tính hợp lệ của một đường dẫn:
	- `exists()`: kiểm tra liệu đường dẫn đó có tồn tại hay không
	- `is_dir()`: kiểm tra liệu đường dẫn có chỉ đến một thư mục hay không
	- `is_file()` : kiểm tra liệu đường dẫn có chỉ đến một tệp hay không
	```python
	print(book.exists()) # True 
	print(book.is_dir()) # True 
	print(book.is_file()) # False
	```
- 2 phương thức sau đây dùng để liệt kê thành phần trong thư mục:
	- `glob()` cho phép liệt kê các đường dẫn phù hợp một quy luật glob:
		```python
		for f in current.glob('*.py'):
			print(f)
		#file.py
		#iofile.py
		```
		
		Ngoài ra, ta có thể dùng hai kí hiệu dấu sao `**` để chỉ "thư mục này và tất cả các thư mục con của nó đến thư mục cuối cùng":
		```python
		for f in current.glob('**/*.py'):
			print(f)
		
		#file.py
		#iofile.py
		#subfold/sub.py
		#subfold/s/s.py
		```
		Đây là cấu trúc của thư mục hiện tại:
		```
		.
		├── data.txt
		├── file.py
		├── iofile.py
		└── subfold
	    ├── s
	    │   └── s.py
	    └── sub.py
		```
	- `iterdir()` được dùng để liệt kê tất cả các đường dẫn con nằm trong đường dẫn hiện tại:
		```python
		for f in current.iterdir():
			print(f)
		
		#data.txt
		#file.py
		#iofile.py
		#subfold
		```
- Các phương thức liệt kê chủ sở hữu của thư mục/file:
	- `owner()` trả về người dùng sở hữu file/thư mục:
	- `group()` trả về nhóm sở hữu file/thư mục:
	 ```python
	 current = Path('data.txt')
	print('owner: {}'.format(current.owner())) # owner: luong
	print('group: {}'.format(current.group())) # group: luong
	```
- Các phương thức tạo mới thư mục / file:
	- `mkdir(mode=0o777, parents=False,exist_ok=False)` tạo thư mục mới, nếu `parents=True` thì tạo cả các thư mục mẹ bên ngoài
	- `touch(mode=0o666, exist_ok=True)` tạo file mới hoặc thay đổi thời gian chỉnh sửa file thành thời điểm hiện tại 
	- Nếu tham só `exist_ok=True` và đường dẫn đã tồn tại trong hệ thống, sẽ chỉnh sửa thời gian sửa đổi file/thư mục, ngược lại sẽ sinh lỗi `FileExistsError`
	Ví dụ:
	```python
	newFile = Path('new.txt')
	newFolder = Path('subfold/hmm/hello')
	newFile.touch()
	newFolder.mkdir(parents=True)
	```
	Sau khi chạy, cấu trúc file:
	```
	.
	├── data.txt
	├── file.py
	├── iofile.py
	├── new.txt
	└── subfold
	    ├── hmm
	    │   └── hello
	    ├── s
	    │   └── s.py
	    └── sub.py
	```
	Thư mục và file mới sẽ có quyền truy cập là `mode`, xem thêm tại [đây](https://www.linuxfoundation.org/blog/blog/classic-sysadmin-understanding-linux-file-permissions)
Ta có thể thay đổi quyền truy cập file/thư mục với `chmod(mode)`
```python
newFile = Path('new.txt')
newFile.chmod(0o761)
```
Dưới đây là sự thay đổi của hệ thống tệp trước và sau khi chạy chương trình:
```
[luong@luongpc files]$ ls -lah
total 24K
drwxr-xr-x 3 luong luong 4.0K Jun 17 09:34 .
drwxr-xr-x 3 luong luong 4.0K Jun 15 14:17 ..
-rw-r--r-- 1 luong luong    5 Jun 17 08:46 data.txt
-rw-r--r-- 1 luong luong   73 Jun 17 09:34 file.py
-rw-r--r-- 1 luong luong   69 Jun 17 08:46 iofile.py
**-rw-r--r-- 1 luong luong    0 Jun 17 09:30 new.txt**
drwxr-xr-x 4 luong luong 4.0K Jun 17 09:30 subfold
[luong@luongpc files]$ python file.py 
[luong@luongpc files]$ ls -lah
total 24K
drwxr-xr-x 3 luong luong 4.0K Jun 17 09:34 .
drwxr-xr-x 3 luong luong 4.0K Jun 15 14:17 ..
-rw-r--r-- 1 luong luong    5 Jun 17 08:46 data.txt
-rw-r--r-- 1 luong luong   73 Jun 17 09:34 file.py
-rw-r--r-- 1 luong luong   69 Jun 17 08:46 iofile.py
**-rwxrw---x 1 luong luong    0 Jun 17 09:30 new.txt**
drwxr-xr-x 4 luong luong 4.0K Jun 17 09:30 subfold
```

- Làm việc với file:
	- `open(mode='r')` để mở file nếu đọc thì `mode=r`, viết thì `mode=w`, trả về một đối tượng kiểu `_io.TextIOWrapper`, xem thêm [Bài 11: Nhập xuất với tệp](../language/11_FileIO.md)
	- `write_text()` và `write_bytes()` để mở file, viết vào file dưới dạng văn bản hoặc nhị phân, rồi đóng file
	- `read_text()` và `read_bytes()` để mở file, đọc từ file dưới dạng văn bản hoặc nhị phân, rồi đóng file.
Ví dụ
```
data.txt:
luong
```

```python
p = Path('data.txt')
f = p.open(mode='r')
print(f.read()) # luong
f.close()
print(p.read_text()) # luong
p.write_text('hello')
```

Sau khi chạy:
```data.txt
hello
```

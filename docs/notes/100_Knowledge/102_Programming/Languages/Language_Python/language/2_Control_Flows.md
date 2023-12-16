---
categories:
  - python-modules
share: true
---



# Bài 2: Các cấu trúc điều khiển (control flows)
## I. Khối lệnh và lùi đầu dòng (indentation)
- Trong Python, các lệnh cùng các khoảng lùi đầu dòng tạo thành một _khối lệnh_
- Ví dụ:
```python
if a = 2:
	# đây là một khối
	print(a)
	print(2*a)
# nằm ngoài khối, tiếp tục
```
## II. Cấu trúc rẽ nhánh
### 1. if-elif-else
Cấu trúc rẽ nhánh với if có cấu trúc như sau:

>[!code] Cấu trúc rẽ nhánh với if
>```python
>if <điều kiện>:
>	# khối lệnh t
>[elif <điều kiện 1>:
>	# khối lệnh e1
>elif <điều kiện 2>:
>	#khối lệnh e2
>...
>else:
>	#khối lệnh e
>]
>```

- Phần trong ngoặc vuông là tùy chọn, có thể có hoặc không
- <điều kiện> là các phép toán hoặc [hàm](./3_Functions.md) trả về kết quả của kiểu dữ liệu `bool`
>[!notes] Kiểu dữ liệu `bool`
>- Là viết tắt của "boolean", kiểu dữ liệu này chỉ có hai giá trị: đúng (true) hoặc sai (false)
>- Kiểu dữ liệu này có thể là kết quả của hàm hoặc các _toán tử so sánh_ như _==, > , <, >=, <=_,..

- Nếu <điều kiện> đúng, khối lệnh t được thực thi
- Nếu <điều kiện> không đúng, chương trình kiểm tra đến câu lệnh elif tiếp theo, cho đến khi gặp câu lệnh else thì chạy khối lệnh _ngay dưới đó_
- Ví dụ:
```python
number = int(input("Enter a number: "))
if number % 6 == 0 :
    print(str(number) +  " chia het cho 6")
    print(str(number) + " /6 = " + str(int(number) // 6))
elif number % 3 == 0:
    print(str(number) + " khong chia het cho 6 nhung chia het cho 3")
else:
    print(number)
```

Chạy:
```plain
Enter a number: 7
7
Enter a number: 6
6 chia het cho 6
6 /6 = 1
Enter a number: 9
9 khong chia het cho 6 nhung chia het cho 3
```

### 2. match-case
- Match-case cho phép so sánh giá trị cần kiểm tra với các giá trị cho trước, tìm được giá trị khớp sẽ thực thi khối lệnh ở dưới giá trị đó:
>[!code] Cấu trúc match-case
>```python
>match <tên biến>:
>	case <giá trị 1>:
>		khối lệnh 1
>	case <giá trị 2>:
>		khối lệnh 2
>	....
>``` 

Ví dụ:
```python 
number = int(input("Enter a number: "));

match number:
    case 1:
        print("one")
    case 2:
        print("two")
    case 3:
        print ("three")
    case 4:
        print ("four")


```

## II. Cấu trúc lặp
### 1. Vòng lặp while
>[!code] Cấu trúc vòng lặp while
>```python
>while <điều kiện>:
>	khối lệnh
>```

Vòng lặp **while** có tác dụng lặp khối lệnh _cho đến khi_ điều kiện _sai_.
Ví dụ minh họa:
```python
number = 5
i = 0
while i<5:
    print(i)
    i += 1
```
Kết quả sau khi chạy code như sau:
```
0
1
2
3
4
```
Sau khi in ra `4`, ta tăng giá trị của i lên 1, lúc này giá trị của i là 5, khiến cho điều kiện _sai_, kết thúc vòng lặp.

### 2. Câu lệnh break
`break` được dùng để thoát sớm vòng lặp. Khi gặp `break`, vòng lặp hiện tại sẽ bị ngưng ngay lập tức:
Ví dụ:
```python
number = 5
i = 0
while i<10:
    print(i)
    i += 1
    if(i==5):
        break
```
Kết quả chạy:
```
0
1
2
3
4
```

Khi gặp i = 5, chương trình thoát hoàn toàn ra khỏi vòng lặp.

### 3. Khối lệnh else với vòng lặp while
- Nếu ta thêm một khối lệnh else vào sau cấu trúc của while ta sẽ có cấu trúc:
```python
while <điều kiện>
	khối lệnh 1
else
	khối lệnh 2
```

- Khối lệnh else sẽ được thực thi nếu vòng lặp while kết thúc tự hiên (không dùng break)
Ví dụ:
```python
number = int(input("enter a number: "))
i = 0
while i<number:
    print(i)
    i += 1
    if(i==7):
        break
else :
    print("1 to " + str(number))
```

Chạy thử:
(1):
```
enter a number: 4
0
1
2
3
1 to 4
```
(2):
```
enter a number: 8
0
1
2
3
4
5
6
```

Ở lần chạy đầu tiên, `i` không thể vượt quá 7, nên không có lệnh `break`. Vòng lặp được thoát tự nhiên, khối lệnh sau `else` được thi hành
Ở lần chạy thứ hai, khi `i` có giá trị là 7, ta có lệnh `break` nên khối lệnh sau else không được thi hành

### 4. Cấu trúc lặp với for
Xem thêm: [ Danh sách](./4_Lists.md)

Vòng lặp `for` trong python cho phép duyệt qua một mảng/danh sách bằng cách lần lượt gán các phần tử của danh sách đó cho một biến. Cấu trúc:

>[!code] Cấu trúc for
>```python
>for <biến> in <danh sách>:
>	khối lệnh
>```
>

Ví dụ:

```python
list_ = [1,2,3]

for i in list_:
    print(i)
```

Kết quả chạy:
```
1
2
3
```

Ta cũng có thể dùng `break` và `else` với `for` tương tự với `while`

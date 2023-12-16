---
share: true
---

#summer #programming 
9_pyinputplus
Ngày 11 tháng 06 năm 2023 
Thời gian tạo:  09:15:13

# Bài 9 Kiểm tra đầu vào với module `pyinputplus`

Repo của module: [asweigart/pyinputplus](https://github.com/asweigart/pyinputplus)

## I. Cơ bản về module `pyinputplus`
- Hàm `input()` của Python cho phép ta nhập một xâu từ bàn phím và trả về xâu đó. Tuy nhiên để làm việc với những đầu vào phức tạp hơn, module `pyinputplus` cung cấp các hàm giúp ta xử lí đầu vào và cung cấp các tính năng hữu ích
- `pyinputplus` không phải là module thuộc thư viện chuẩn Python, nên khi dùng ta cần tải về từ `pip`:
``` 
pip3 install pyinputplus # linux
```
- Sau đó ta cần nhập module để sử dụng:
```python
import pyinputplus as pyip
```
- Các tính năng chính của module:
	- Cho phép nhập đầu vào theo một kiểu dữ liệu xác định dựa trên các điều kiện xác định, nếu không thỏa mãn sẽ yêu cầu nhập lại
	- Cho phép timeout và giới hạn số lần nhập dữ liệu
	- Sử dụng [biểu thức chính quy](./8_re.md) để kiểm tra thông tin nhập vào
## II. Họ phương thức `input*()`:
Dưới đây là các phương thức nhập cơ bản của `pyinputplus` và tác dụng của chúng:

|Phương thức|Đầu vào cho phép|Các giá trị trả về|
|---|---|---|
|`inputStr`|xâu kí tự|xâu kí tự|
|`inputNum`|số nguyên hoặc số thực|số nguyên hoặc số thực|
|`inputInt`|số nguyên|số nguyên|
|`inputFloat`|số thực|số thực|
|`inputBool`|các giá trị `T`,`F`,`True`,`False`, không phân biệt chữ hoa chữ thường|True hoặc False|
|`inputYesNo`|các giá trị `Yes`,`No`,`yes`,`no`, không phân biệt chữ hoa chữ thường|`yes` hoặc `no`|
|`inputChoice`|các giá trị nằm trong một danh sách cho trước|các giá trị nằm trong danh sách cho trước|
|`inputMenu`|giống `inputChoice`|giống `inputChoice`|
|`inputDateTime`|ngày tháng và giờ|dữ liệu thuộc kiểu `datetime.datetime`|
|`inputDate`|ngày|dữ liệu thuộc kiểu `datetime.date`|
|`inputTime`|giờ|dữ liệu thuộc kiểu `datetime.time`|

Ngoài tham số `prompt` biểu diễn dòng nhắc lệnh để người dùng nhập dữ liệu:
- Các phương thức `inputChoice` và `inputMenu` có tham số `choices` là một danh sách các lựa chọn
- 3 phương thức liên quan đến thời gian có tham số `formats` chỉ định dạng ngày giờ

Dưới đây là một ví dụ minh họa sử dụng `inputNum()` và `inputMenu`:

```python
num = pyip.inputNum('Enter a number: ')
print('You\'ve entered number: {}'.format(num))
```

```
Enter a number: a
'a' is not a number.
Enter a number: 
Blank values are not allowed.
Enter a number: 8.9
You've entered number: 8.9
```

```python
colors = ['red','yellow','green','blue','cyan','magenta','black','white']
favouriteColor = pyip.inputMenu(colors,'Choose your favourite color: \n')
print(f'Your favourite color is {favouriteColor}')
```

```
Choose your favourite color: 
* red
* yellow
* green
* blue
* cyan
* magenta
* black
* white
gray
'gray' is not a valid choice.
Choose your favourite color: 
* red
* yellow
* green
* blue
* cyan
* magenta
* black
* white
red
Your favourite color is red
```
## III. Các tham số:
- `blank` (boolean) : nếu là `True` sẽ cho phép người dùng bỏ qua phần nhập, tức là phần nhập trống:
```python
text = pyip.inputStr('You can enter something: ',blank=True)
print(f'text:\'{text}\'')
```
```
You can enter something: 
text:''
```
- `min`,`max` (number): xác định giá trị lớn nhất và nhỏ nhất có thể chấp nhận của đầu vào
```python
num = pyip.inputNum('Enter a number from 1-20, inclusive: ',min=1,max=20)
print(f'You\'ve entered {num}')
```
```
Enter a number from 1-20, inclusive: -2
Number must be at minimum 1.
Enter a number from 1-20, inclusive: 25
Number must be at maximum 20.
Enter a number from 1-20, inclusive: 1
You've entered 1
```
- `greaterThan`,`lessThan` (number) yêu cầu đầu vào lớn hơn và nhỏ hơn một giá trị nào đó:
```python
num = pyip.inputNum('Enter a number between 100 and 200, exclusive: ',greaterThan=100,lessThan=200)
print(f'You\'ve entered {num}')
```
```
Enter a number between 100 and 200, exclusive: 24 
Number must be greater than 100.
Enter a number between 100 and 200, exclusive: 225
Number must be less than 200.
Enter a number between 100 and 200, exclusive: 100
Number must be greater than 100.
Enter a number between 100 and 200, exclusive: 200
Number must be less than 200.
Enter a number between 100 and 200, exclusive: 124
You've entered 124
```
(4 tham số trên chỉ dành cho các phương thức nhận đầu vào số)
- `timeout`, `limit`: biểu diễn thời gian tối đa để nhập và số lần nhập lại tối đa. Nếu vượt quá giá trị này sẽ đưa ra lỗi `TimeoutException` hoặc `RetryLimitException`. Một tham số khác đi kèm là `default`, là giá trị trả về mặc định mà không gây lỗi:
```python
ret = pyip.inputStr('Quick, enter something in the next 5 seconds: ',timeout=5,default='Nothing')
print(f'ret={ret}')
choice = ['a','b','c','d']
ret = pyip.inputChoice(choice,'a b c or d: ',limit=3,default='a')
print(f'ret={ret}')
```
```
Quick, enter something in the next 5 seconds: something
ret=Nothing
a b c or d: e
'e' is not a valid choice.
a b c or d: f
'f' is not a valid choice.
a b c or d: g
'g' is not a valid choice.
ret=a
```
- `blockRegexes` và `allowRegexes` là danh sách biểu thức chính quy được dùng để đối chiếu với đầu vào. Đầu vào không được chứa các biểu thức trong `blockRegexes` nhưng được phép chứa các biểu thức trong `allowRegexes`. `allowRegexes` ghi đè `blockRegexes`
```python
word = pyip.inputStr('Enter an word with more than 3 character: or the word \'hey\': ',blockRegexes=[r'^\w{,3}$'],allowRegexes=[r'^hey$'])
print(word)
```

Trong ví dụ trên, `inputStr` không chấp nhận các từ có dưới 3 kí tự trừ từ `hey`:
```
$ python input.py
Enter an word with more than 3 character: or the word 'hey': af   
This response is invalid.
Enter an word with more than 3 character: or the word 'hey': afsjsf
afsjsf
$ python input.py 
Enter an word with more than 3 character: or the word 'hey': hey
hey
```
Với blockRegexes, danh sách có thể chứa các tuple, với phần tử đầu tiên là regex bị chặn, phần tử thứ hai là thông báo khi gặp rege đó:
```python
word = pyip.inputStr('Enter an word with more than 3 character: or the word \'hey\': ',blockRegexes=[(r'^\w{,3}$','too short')],allowRegexes=[(r'^hey$')])
print(word)
```
```
Enter an word with more than 3 character: or the word 'hey': l 
too short
Enter an word with more than 3 character: or the word 'hey': cql
too short
Enter an word with more than 3 character: or the word 'hey': als;fkjas;f
als;fkjas;f
```
- `yesVal` và `noVal` trong `inputYesNo` cho phép custom `yes` hoặc `no` theo ý thích

---
Edit history: 
- Sửa đổi vào 08:22:55 Ngày 12 tháng 06 năm 2023


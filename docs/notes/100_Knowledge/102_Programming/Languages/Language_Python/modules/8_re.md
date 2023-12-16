---
share: true
---


#summer #programming #lang/py 
8_RegEx
Ngày 08 tháng 06 năm 2023 
Thời gian tạo:  20:38:42

Date created: 08-06-2023 

# Bài 8: Xử lí biểu thức chính quy với module `re`
Xem thêm tại: [re](https://docs.python.org/3/library/re.html)
## I. Cái quái gì đây

>[!notes] Khái niệm
>**Regular Expression - RegEx (Biểu thức chính quy)**, theo [Wikipedia](https://vi.wikipedia.org/wiki/Bi%E1%BB%83u_th%E1%BB%A9c_ch%C3%ADnh_quy), là một _xâu_ miêu tả một _bộ xâu_ khác, theo những _quy tắc_ nhất định

- Ví dụ, `'gr(a|e)y'` miêu tả bộ xâu `('gray','grey')`.

- RegEx thường được dùng trong việc tìm nhanh văn bản theo quy luật có sẵn trong xâu, như số điện thoại, mã, v.v...

## II. Module `re` để làm việc với biểu thức chính quy


Để tìm nhanh phần văn bản theo quy luật với RegEx, ta cần dùng một module của python tên `re`.
```python
import re
```

### 1. So khớp mẫu (pattern matching) cơ bản
- Để tạo một mẫu (pattern), ta dùng phương thức `.compile(str)` cùng một xâu biểu diễn mẫu cần so khớp:

```python
dateRegex = re.compile(r'\d\d-\d\d-\d\d\d\d')
```
Với `'\d'` biểu diễn mọi chữ số từ `0-9`. Xem thêm các quy tắc khác tại [Quy tắc biểu thức chính quy](RegEx_Patterns.md)
Một số kí tự thường gặp:

|Kí tự|Khớp với|
|---|---|
|`\d`|Mọi chữ số từ 0-9|
|`\D`|Mọi kí tự không phải chữ số từ 0-9|
|`\w`|Các kí tự chữ cái, chữ số và dấu gạch dưới|
|`\W`|Mọi kí tự trừ chữ cái, chữ số, dấu gạch dưới|
|`\s`|Các kí tự khoảng trống, tab, xuống dòng|
|`\S`|Mọi kí tự trừ khoảng trống, tab, xuống dòng|

- `dateRegex` thuộc kiểu `Pattern`, biểu diễn một mẫu để tìm trong xâu.

- Để tìm trong một xâu những đoạn khớp vỡi mẫu cho trước, ta dùng phương thức `.search(str)` với `str` là xâu cần so khớp. Phương thức này trả về một biến kiểu `Match`, chứa các thông tin về phần văn bản được so khớp

```python
text = 'Date created: 08-06-2023'
date = dateRegex.search(text)
```
- Để hiển thị phần văn bản tìm được ta dùng phương thức `.group()`:

```python
print(date.group()) # 08-06-2023
```
- Nếu không tìm thấy phần văn bản khớp với mẫu cho trước, phương thức `.search()` trả về `None`:
```python
text = 'Date created'
date = dateRegex.search(text)
print(date) # None
```


### 2. Nhóm phần so khớp
- Ta có thể nhóm các phần cần thiết trong mẫu so khớp với dấu ngoặc đơn `()`. 
```python
dateRegex = re.compile(r'(\d\d)-(\d\d)-(\d\d\d\d)')
```
- Sau khi tìm được văn bản so khớp thành công, ta có thể lấy được các nhóm này với phương thức `.group()`. Các nhóm được đếm từ 1, truyền giá trị 0 hoặc không truyền giá trị sẽ trả về toàn bộ xâu:
```python
print(date.group(0)) # 08-06-2023
print(date.group(1)) # 08
print(date.group(2)) # 06
print(date.group(3)) # 2023
```
- Ngoài ra phương thức `.groups()` trả về một [tuple](../language/5_Mutable_Immutable.md#3.%20Kiểu%20dữ%20liệu%20tuple) chứa tất cả các nhóm:

```python
print(date.groups()) # ('08', '06', '2023')
```

Trong các ví dụ sau ta sẽ dùng hàm sau để in ra màn hình phần được so khớp:
```python
def printMatch(regexMatch):
	if regexMatch == None:
		print('Not found')
	else:
		print("Found: '{0}'".format(regexMatch.group()))
```

### 3. Gộp nhóm so khớp
Cú pháp `a|b` sẽ khớp với `a` hoặc `b`:
```python
text0 = 'Date created: 09-06/2023'
dateRegex0 = re.compile(r'\d\d(-|/)\d\d(-|/)\d\d\d\d')
print(dateRegex0.search(text0).group()) # 09-06/2023
```

### 4. Định lượng so khớp
- Kí tự `?`: khớp với _không_ hoặc _một_ lần lặp của nhóm trước nó:
- Kí tự `*` : khớp với _ít nhất không_ lần lặp của nhóm trước nó
- Kí tự `+` : khớp với _ít nhất một_ lần lặp của nhóm trước nó
- Cú pháp `{n}` : khớp với _đúng `n`_ lần lặp của nhóm trước nó
- Cú pháp `{min,max}`: khớp với _ít nhất `min` và nhiều nhất `max`_ lần lặp của nhóm trước nó
Trong "siêu ví dụ" dưới đây, ta lấy 6 mẫu so vào 5 xâu khác nhau :

```python
text20 = 'everyone'
text21 = 'helloeveryone'
text22 = 'hellohelloeveryone'
text23 = 'hellohellohelloeveryone'
text24 = 'hellohellohellohelloeveryone'

rules = [
r'(hello)?',
r'(hello)*',
r'(hello)+',
r'(hello){2}',
r'(hello){2,4}',
r'(hello){2,4}?',
]
texts = [text20,text21,text22,text23,text24]

for rule in rules:
	print('Current pattern: {0}'.format(rule))
	regex = re.compile(rule)
	for text in texts:
		print('''searching in '{0}': '''.format(text),end='')
		printMatch(regex.search(text))
```
Dưới đây là kết quả:

```
Current pattern: (hello)?
searching in 'everyone': Found: ''
searching in 'helloeveryone': Found: 'hello'
searching in 'hellohelloeveryone': Found: 'hello'
searching in 'hellohellohelloeveryone': Found: 'hello'
searching in 'hellohellohellohelloeveryone': Found: 'hello'
Current pattern: (hello)*
searching in 'everyone': Found: ''
searching in 'helloeveryone': Found: 'hello'
searching in 'hellohelloeveryone': Found: 'hellohello'
searching in 'hellohellohelloeveryone': Found: 'hellohellohello'
searching in 'hellohellohellohelloeveryone': Found: 'hellohellohellohello'
Current pattern: (hello)+
searching in 'everyone': Not found
searching in 'helloeveryone': Found: 'hello'
searching in 'hellohelloeveryone': Found: 'hellohello'
searching in 'hellohellohelloeveryone': Found: 'hellohellohello'
searching in 'hellohellohellohelloeveryone': Found: 'hellohellohellohello'
Current pattern: (hello){2}
searching in 'everyone': Not found
searching in 'helloeveryone': Not found
searching in 'hellohelloeveryone': Found: 'hellohello'
searching in 'hellohellohelloeveryone': Found: 'hellohello'
searching in 'hellohellohellohelloeveryone': Found: 'hellohello'
Current pattern: (hello){2,4}
searching in 'everyone': Not found
searching in 'helloeveryone': Not found
searching in 'hellohelloeveryone': Found: 'hellohello'
searching in 'hellohellohelloeveryone': Found: 'hellohellohello'
searching in 'hellohellohellohelloeveryone': Found: 'hellohellohellohello'
Current pattern: (hello){2,4}?
searching in 'everyone': Not found
searching in 'helloeveryone': Not found
searching in 'hellohelloeveryone': Found: 'hellohello'
searching in 'hellohellohelloeveryone': Found: 'hellohello'
searching in 'hellohellohellohelloeveryone': Found: 'hellohello'
```

### 5. So khớp "tham lam" và so khớp "lười biếng"
Xét hai mẫu cuối cùng:
```
(hello){2,4}
(hello){2,4}?
```
- Đối với `(hello){2,4}`, python sử dụng phương pháp so khớp mẫu "tham lam" (greedy), sẽ tìm xâu con _dài nhất_ phù hợp với mẫu. Với ví dụ có 2,3,4 từ 'hello', ta đều nhận được xâu khớp có 2,3,4 từ 'hello', vì đây là phần dài nhất hợp với mẫu, có từ 2-4 từ 'hello'
- Khi ta thêm kí tự `?` vào đằng sau, ta chuyển sang phương pháp "lười biếng" (lazy), sẽ tìm xâu _ngắn nhất_ phù hợp với mẫu. Với ví dụ có 2,3,4 từ 'hello', ta chỉ nhận được xâu khớp có hai từ 'hello' mà thôi
>[!important] Lưu ý
>Thêm kí tự `?` vào các mẫu có giá trị trả về với nhiều độ dài khác nhau sẽ chuyển về phương pháp lazy, tìm xâu ngắn nhất hợp với mẫu.
### 6. Tìm tất cả các xâu con trùng khớp
- Phương thức `findall` sẽ tìm tất cả các phần trùng khớp theo quy luật. Phương thức này trả về:
	- [Danh sách](../language/4_Lists.md) gồm các xâu trùng khớp nếu trong quy luật không có nhóm
	- Danh sách gồm các [tuple](../language/5_Mutable_Immutable.md#3.%20Kiểu%20dữ%20liệu%20tuple) chứa từng nhóm của từng phần so được

```python
information = 'Mrs. Johnson invited Mr. Smith and Mrs. Brown to her party, where they met Mr. Davis and Mrs. Rodriguez for the first time.'

names = re.compile(r'Mrs?\. \w+')
print(names.findall(information))
# ['Mrs. Johnson', 'Mr. Smith', 'Mrs. Brown', 'Mr. Davis', 'Mrs. Rodriguez']
names = re.compile(r'((Mrs?\.) \w+)')
print(names.findall(information))
# [('Mrs. Johnson', 'Mrs.'), ('Mr. Smith', 'Mr.'), ('Mrs. Brown', 'Mrs.'), ('Mr. Davis', 'Mr.'), ('Mrs. Rodriguez', 'Mrs.')]
```

### 7. Lớp kí tự
- Kí tự `.` : khớp với _mọi kí tự_, từ kí tự `\n`
- Cú pháp `[...]` khớp với mọi kí tự _nằm trong_ cặp ngoặc
- Cú pháp `[^...]` khớp với mọi kí tự _trừ_ các kí tự _nằm trong_ cặp ngoặc

```python
text4 = 'Yesterday, I ran 5 miles in 35 minutes and burned 400 calories.'
vowel = re.compile(r'[aeiou]')
print(vowel.findall(text4))
# ['e', 'e', 'a', 'a', 'i', 'e', 'i', 'i', 'u', 'e', 'a', 'u', 'e', 'a', 'o', 'i', 'e']
notVowel = re.compile(r'[^aeiou]')
print(notVowel.findall(text4))
# ['Y', 's', 't', 'r', 'd', 'y', ',', ' ', 'I', ' ', 'r', 'n', ' ', '5', ' ', 'm', 'l', 's', ' ', 'n', ' ', '3', '5', ' ', 'm', 'n', 't', 's', ' ', 'n', 'd', ' ', 'b', 'r', 'n', 'd', ' ', '4', '0', '0', ' ', 'c', 'l', 'r', 's', '.']
```

```python
gibberish = 'af\n\t  '
character = re.compile('.')
print(character.findall(gibberish))
# ['a', 'f', '\t', ' ', ' ']
```

### 8. Bắt đầu hoặc kết thúc
- Cú pháp `^s`yêu cầu xâu _bắt đầu_ bằng `s`
- Cú pháp `s$` yêu cầu xâu _kết thúc_ bằng `s`

```python
greeting = 'Hello my name is Luong'
introducing = 'He says hello'

beginsWithHello = re.compile('^Hello')
endsWithHello = re.compile('hello$')

printMatch(beginsWithHello.search(greeting)) # Found: 'Hello'
printMatch(beginsWithHello.search(introducing)) # Not found
printMatch(endsWithHello.search(greeting)) # Not found
printMatch(endsWithHello.search(introducing)) # Found: 'hello'
```
- Khi dùng cả hai kí hiệu `^s$` ta yêu cầu xâu _phải giống hệt_ xâu `s`
### 9. Thay thế các xâu so được
- Ta dùng phương thức `pattern.sub(sub,str)` để thay thế toàn bộ các xâu con hợp với quy luật `pattern` trong xâu `str` bằng xâu `sub`
- Để sử dụng lại các nhóm so được, ta dùng cú pháp `\n` trong `sub` với n là vị trí nhóm để lấy nội dung so khớp của nhóm đó, tương tự `pattern.search(str).group(n)`

```python
information = 'Mrs. Johnson invited Mr. Smith and Mrs. Brown to her party, where they met Mr. Davis and Mrs. Rodriguez for the first time.'
names = re.compile(r'((Mrs?\.) \w+)')
print(names.sub(r'\2 ****',information))
# Mrs. **** invited Mr. **** and Mrs. **** to her party, where they met Mr. **** and Mrs. **** for the first time.
```

### 10. Các chế độ so khớp
- `re.IGNORECASE` để không phân biệt chữ hoa, chữ thường khi so khớp
```python
text3a = 'hello Hello hElLo'
hello = re.compile('Hello',re.IGNORECASE)
print(hello.findall(text3a)) # ['hello', 'Hello', 'hElLo']
```
- `re.DOTALL` làm cho kí tự `.` khớp với _mọi kí tự_, kể cả `\n`

```python
gibberish = 'af\n\t  '
allCharacter = re.compile('.',re.DOTALL)
print(allCharacter.findall(gibberish))
# ['a', 'f', '\n', '\t', ' ', ' ']
```

- `re.VERBOSE` để bỏ qua khoảng trắng và chú thích chương trình trong xâu quy luật, cho phép ta giải thích từng phần trong pattern:

```python
text3 = 'Date created: 09/6/2023'
dateRegex3 = re.compile(
r'''
\d?\d(-|/)  # day
\d?\d(-|/)  # month
\d\d\d\d''' # year
,re.VERBOSE
)
print(dateRegex3.search(text3).group()) # 09/6/2023
```


---
share: true
---

#summer #programming #lang/py 

# Bài 7: Kiểu dữ liệu xâu (`str`)
- `str`, hay xâu là một dãy các kí tự (thực chất là **code point**) unicode
- `str` là kiểu dữ liệu [immutable](./5_Mutable_Immutable.md)

## 1. Hằng xâu
Một **hằng xâu (string literal)** có thể được biểu diễn theo ba cách:
- Cách đầu tiên: đặt giữa hai dấu nháy đơn `''`:
`'hello'`
- Cách thứ hai: đặt giữa hai dấu nháy kép: `""`:
`"I'm Leafer"`
Đối với hai cách trên, để thêm các kí tự đặc biệt ta cần các **escape sequence**:

|Escape sequence|Đầu ra|
|---|---|
|`\'`|'|
|`\"`|"|
|`\n`|xuống dòng|
|`\t`|tab|
|`\\`|\\|

Ta có thể bỏ qua tất cả các escape sequence này và lấy được xâu nguyên dạng với **xâu thô (raw string)**. Đặt tiền tố `r` trước hằng xâu, và mọi escape sequence sẽ được xử lí như bình thường, ví dụ:
`r'hello everyone \n my name is\' leafer `
sẽ in ra y nguyên xâu `hello everyone \n my name is\' leafer`

- Cách thứ ba: dùng tam nháy đơn hoặc tam nháy kép: những hằng xâu này cho phép xuống dòng và các kí tự đặc biệt như `'` và `"`, ví dụ:
```
'''hello everyone
my name's leafer
welcome to the vault
```

## 2. Định dạng xâu với `f-string` và `.format()`
- **Formatted string literal (viết tắt: f-string)** với tiền tố f cho phép ta đưa các giá trị biểu thức vào bên trong xâu, cú pháp như sau:
```
f'...{<biểu thức>}...'
```
Trong đó, giá trị của `<biểu thức>` sẽ được tính toán và đưa vào vị trí tương ứng của xâu, ví dụ:

```python
print(f'num * 2 = {num*2}')
# output: num * 2 = 20
```
Nếu làm việc với số thực, ta thường cần định dạng số lượng chữ số thập phân cần in ra. Để làm điều này ta dùng hậu tố `:a.b` theo sau biểu thức. `a` là chiều dài phần được dành ra để in giá trị biểu thức, `b` là số chữ số thập phân.

Ví dụ:

```python
print(f'num * 2 = {num*2:8.2f}')
# output: num * 2 =    20.23
```

- Ngoài f-string, một cách khác để định dạng xâu với biểu thức bên ngoài là qua phương thức `.format()` với cấu trúc:

```
'...{}...{}...'.format(<danh sách biểu thức>)
```

Trong đó, ở trong các cặp ngoặc kép có thể là:
- số: `{0},{1},{2},...` biểu thị vị trí biểu thức trong danh sách theo vị trí
- từ khóa đặc biệt, lúc này bên trong phép gọi phương thức `.format()` cần có cặp `keyword=value` để truyền cho giá trị này
Cách gọi như vậy tương tự với [truyền đối số cho hàm](./3_Functions.md#VI.%20Truyền%20đối%20số)

Ví dụ:

```python
num1 = 10.1142
num2 = 20
name = 'leafer'

print('name: {name},num2 = {1}, num1 = {0}'.format(num1,num2,name=name))
# name: leafer,num2 = 20, num1 = 10.1142
```

## 3. Các phương thức với xâu
- Xâu cũng là một loại [danh sách](./4_Lists.md), nên các phương thức không làm thay đổi danh sách cũng được áp dụng cho xâu, trong đó có việc lấy xâu con tương tự lấy danh sách con.

### `upper()`,`lower()`
Hai phương thức lần lượt trả về xâu với tất cả kí tự chữ hoa hoặc chữ thường:

```python
name = 'LeaFer'

print(f'''name.upper() : {name.upper()}
name.lower() : {name.lower()}''')

# name.upper() : LEAFER
# name.lower() : leafer
```

### Họ phương thức `isX()`
Các phương thức này kiểm tra một tính chất nào đó của tất cả kí tự trong xâu:

|Tên phương thức|Tính chất kiểm tra|
|---|---|
|isupper()|xâu chỉ chứa chữ hoa?|
|islower()|xâu chỉ chứa chữ thường?|
|isalpha()|xâu chỉ chứa chữ cái?|
|isalnum()|xâu chỉ chứa chữ cái và chữ số?|
|isdecimal()|xâu chỉ chứa chữ số?|
|isspace()|xâu chỉ chứa các kí tự trống, cách, xuống dòng,...?|
|istitle()|các từ trong xâu đều bắt đầu bằng chữ hoa?|

### Phương thức `startswith()` và `endswith()`
`s.startswith(prefix,start,end)`
`s.endswith(suffix,start,end`)

Lần lượt kiểm tra liệu xâu `s[start:end]` có bắt đầu hay kết thúc bằng xâu `prefix` hay `suffix` hay không:
Mặc định, `start=0`, `end=len(s)`


```python
greeting = 'hello everyone'

print(greeting.startswith('he',3,10)) # False
print(greeting.startswith('ev',6))    # True
print(greeting.endswith('one'))       # True
print(greeting.endswith('very',0,11)) # True
```

### Gộp và tách xâu
`s.join(iterable)` nhận một [danh sách](./4_Lists.md)/bộ gồm các xâu, ghép chúng lại cách nhau bằng xâu s:
```python
words = ['Paddle', 'Whimsical', 'Ambiguous', 'Jovial', 'Rambunctious']
print('.'.join(words))
# Paddle.Whimsical.Ambiguous.Jovial.Rambunctious
```
`s.split(sep,maxsplit=-1)` tách xâu s thành một danh sách các xâu. Quá trình tách dựa trên một xâu khác `sep` lặp lại trong s. 
Ví dụ:

```python
things = 'Paddle..Whimsical.Ambiguous.Jovial.Rambunctious' 

words = things.split('.')
print(words) # ['Paddle', '', 'Whimsical', 'Ambiguous', 'Jovial', 'Rambunctious']
```

Nếu truyền `maxsplit`, mảng trả về sẽ có nhiều nhất `maxsplit+1` phần tử. 
```python
words = things.split('.',3)
print(words) # ['Paddle', 'Whimsical', 'Ambiguous', 'Jovial.Rambunctious']
```

Nếu không truyền sep, sẽ mặc định tách theo khoảng trống giữa các từ, ví dụ:

```python
sentence = "The      sun was setting  over the horizon, painting the sky in a warm, golden   glow."
words = sentence.split()
print(words)
# ['The', 'sun', 'was', 'setting', 'over', 'the', 'horizon,', 'painting', 'the', 'sky', 'in', 'a', 'warm,', 'golden', 'glow.']
```

`s.partition(sep)` tách xâu s thành một [bộ](./5_Mutable_Immutable.md#3.%20Kiểu%20dữ%20liệu%20tuple) gồm 3 phần tử: phần xâu trước `sep`, `sep` và phần xâu sau `sep`. Ta tính lần xuất hiện đầu tiên của `sep` trong xâu.

```python
sentence = "The sun was setting over the horizon, painting the sky in a warm, golden glow."
words = sentence.partition('horizon')
print(words)
# ('The sun was setting over the ', 'horizon', ', painting the sky in a warm, golden glow.')
```

Nếu trong xâu không có `sep`, phương thức trả lại bộ 3 gồm xâu và 2 xâu rỗng

```python
sentence = "The sun was setting over the horizon, painting the sky in a warm, golden glow."
words = sentence.partition('sunset')
print(words)
# ('The sun was setting over the horizon, painting the sky in a warm, golden glow.', '', '')
```

### Căn xâu
`s.rjust(width,[fillchar])`
`s.ljust(width,[fillchar])`
`s.center(width,[fillchar])`

Các phương thức này đặt xâu s trong một khoảng trống `width` kí tự, ở bên phải, bên trái hoặc ở giữa, phần khoảng trống sẽ được điền bằng `fillchar`, là một xâu **chỉ có 1 kí tự**

Ví dụ:

```python
title = "LEAFER'S SHOP"

print(title.rjust(50,'*'))
print(title.center(50,))
print(title.ljust(50,'='))
# *************************************LEAFER'S SHOP
#                   LEAFER'S SHOP                   
# LEAFER'S SHOP=====================================
```
Nếu tò mò, việc truyền xâu có nhiều hơn một kí tự vào `fillchar` sẽ gây `TypeError`

### Loại bỏ các kí tự thừa
`s.strip([chars])` : loại bỏ từ cả hai bên
`s.lstrip([chars])` : loại bỏ từ bên trái
`s.rstrip([chars])`: loại bỏ từ bên phải

Nếu không truyền tham số `chars`, phương thức này sẽ loại bỏ các dấu cách:
```python
sentence = '        hello world          '
print(f'|{sentence.strip()}|')  # |hello world|
print(f'|{sentence.lstrip()}|') # |hello world          |
print(f'|{sentence.rstrip()}|') # |        hello world|
```
Nếu truyền tham số `chars`, phương thức sẽ loại bỏ kí tự cho đến khi gặp kí tự không nằm trong xâu được đưa vào:
```python

another = 'defdefdefhelloworlddefdef'
print('|{0}|\n|{1}|\n|{2}|'.format(another.strip('def'),another.lstrip('def'),another.rstrip('def')))
#|helloworl|
#|helloworlddefdef|
#|defdefdefhelloworl|
```

### Hàm `ord()` và `chr()`
Hàm `ord()` lấy một kí tự và trả về mã số Unicode của nó.
Hàm `chr()` lấy một số nguyên và in ra kí tự với mã Unicode đó
Ví dụ: `ord('A') = 91` và `chr(91)='A'`
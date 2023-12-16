---
share: true
---

 %%Tạo mới vào lúc 08:47:08 vào Ngày 19 tháng 06 năm 2023%%
#summer #programming 
12_shelve
Ngày 19 tháng 06 năm 2023 
08:47:12

# Bài 12: Lưu trữ dữ liệu vĩnh viễn với `shelve`
Ngoài việc lưu trữ dữ liệu dưới dạng văn bản thuần túy hoặc các bytes nhị phân, module `shelve` cho phép ta lưu trữ dữ liệu trong file dưới dạng một [từ điển](../language/6_Dictionary.md), giúp việc lưu trữ và truy xuất dữ liệu dễ dàng hơn.

>[!formula] Nhập module
>```python
>import shelve
>```

Để mở một file và một `shelve` với nó, ta dùng phương thức `open()`:
```python
db = shelve.open('data','c')
```
Tham số:
- `filename`: tên file, có thể là [đường dẫn](./10_pathlib.md)
- `flag`: cờ hiệu chỉ loại file: `r` là đọc, `w` là ghi, `c`là cả đọc và ghi, tạo nếu chưa có và `n` là tạo mới và dùng để đọc và ghi
- `writeback`: Nếu để là `False`, các dữ liệu chỉ được ghi vào shelf thông qua phép gán \-True`, dữ liệu sẽ đưa vào bộ đệm, có khả năng tự xử lí và ghi vào trong shelf, giúp dữ liệu [mutable](../language/5_Mutable_Immutable.md#II.%20Hai%20loại%20kiểu%20dữ%20liệu%20Mutable%20và%20Immutable) có khả năng tự thay đổi
- `protocol`: phương thức tuần tự hóa dữ liệu

`db` giờ đây là một từ điển chứa tất cả dữ liệu đã từng ghi trên file `data`. Ta có thể thực hiện mọi thao tác với từ điển trên `db`. Xem thêm [Bài 6: Từ điển](../language/6_Dictionary.md)
Tuy nhiên, nếu muốn thay đổi trực tiếp các dữ liệu mutable trên shelf cần truyền `writeback=True`, ví dụ:

```python
print(db['list'])  # [1, 2, 3, 4, 5]
db['list'].append(6)
print(db['list']) # [1, 2, 3, 4, 5]
```

```python
print(db['list'])  # [1, 2, 3, 4, 5]
db['list'].append(6)
print(db['list']) # [1, 2, 3, 4, 5, 6]
```

Phương thức `sync()` giúp ta lưu trữ lại dữ liệu trên shelf và đồng bộ với file.
Phương thức `close()` dùng để đóng shelf và đóng file. `close()` sẽ tự động gọi `sync()`

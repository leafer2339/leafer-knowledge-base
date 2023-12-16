---
tags:
  - academic
subject: calculus
chapter: 1
unit: 3
title: GTNN, GTLN của hàm số
share: true
---



> Nhật kí chỉnh sửa:
> Tạo mới vào lúc 16:00:52 vào Ngày 15 tháng 06 năm 2023

# Giá trị lớn nhất, giá trị nhỏ nhất của hàm số

>[!note] Tổng quan
>Môn: [Giải tích 12](./101_12_01_giai_tich.md)

>[!formula] Định nghĩa
> Cho hàm số $y = f(x)$ xác định trên $D$
> a) Số $M$ được gọi là **giá trị lớn nhất** của hàm số $y = f(x)$ trên $D$ nếu:
> 	- $f(x) \le M \forall x \in D$
> 	- $\exists x_0 \in D : f(x_0) = M$
> Kí hiệu:
> $$\max_{D}{f(x)} = M$$
> b) Số $m$ được gọi là **giá trị nhỏ nhất** của $y=f(x)$ trên $D$ nếu:
> 	- $f(x) \ge m \forall x \in D$
> 	- $\exists x_0 \in D : f(x_0) = m$
> Kí hiệu:
> $$\min_{D}{f(x)} = m$$

>[!note] Định lí:
>Mọi hàm số _liên tục_ trên một đoạn đều có giá trị lớn nhất và giá trị nhỏ nhất trên đoạn đó
>(điều tương tự không áp dụng cho khoảng)

## Quy tắc tìm giá trị lớn nhất, giá trị nhỏ nhất của hàm số liên tục trên một đoạn
1. Tìm $x_1,x_2,...,x_n$ trên $(a;b)$ tại đó $f'(x) = 0$ hoặc không xác định
2. Tính $f(a),f(x_1),f(x_2),...f(x_n),f(b)$
3. m là số nhỏ nhất trong các số ở bước 2, M là số lớn nhất
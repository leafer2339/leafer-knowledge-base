---
tags:
  - academic
subject: calculus
chapter: 2
unit: 5
title: Khái niệm và hàm số lũy thừa, logarithm
share: true
---



%%Tạo mới vào lúc 07:49:19 vào Ngày 26 tháng 06 năm 2023%%

# Lũy thừa và Logarith

>[!note] Tổng quan
>Môn: [Giải tích 12](./101_12_01_giai_tich.md)

## Khái niệm về lũy thừa

>[!formula] Lũy thừa với số mũ nguyên
>Với $n \in Z^+$ và số thực $a$, **lũy thừa bậc n** của a được xác định bởi:
>$$a^n = a.a.a. ... .a$$(n thừa số a)
>$a$ là **cơ số**, còn $n$ là **số mũ**

Một số quy tắc:
$$a^0=1(a\neq 0)$$
$$a^{-n} = \frac{1}{a^n}$$
$$0^n = 0 (n>0)$$

>[!formula] Căn bậc n
>Cho số thực $b$ và số nguyên dương n $n\ge 2$, $a$ được gọi là **căn bậc n** của $b$ nếu $$a^n = b$$, kí hiệu $a = \sqrt[n]{b}$

Tính chất:
$$\sqrt[n]{a} . \sqrt[n]{b} = \sqrt[n]{a.b}$$
$$(\sqrt[n]{a})^m = \sqrt[n]{a^m}$$
$$\sqrt[n]{\sqrt[k]{a}} = \sqrt[n.k]{a}$$

$$\sqrt[n]{a^n} = \begin{cases} a \text{ (n lẻ) }\\ |a| \text{ (n chẵn) } \end{cases}$$

>[!formula] Lũy thừa với số mũ hữu tỉ
>Cho số thực $a$ dương và số hữu tỉ $r = \frac{m}{n}$ với $m \in Z$, $n \in N, n\ge 2$ ta có: $$a^r = \sqrt[n]{a^m}$$

Với số vô tỉ $r$, ta có nhận xét: "Luôn tồn tại dãy số hữu tỉ $(r_n)$" có giới hạn là $r$ và giới hạn của dãy số $a^{r_n}$ không phụ thuộc vào cách chọn $(r_n)$

>[!formula] Lũy thừa với số mũ vô tỉ
>$$a^{r} = \lim_{n \rightarrow +\infty}{a^{r_n}}, r = \lim_{n \rightarrow +\infty}{r_n}$$

## Tính chất của lũy thừa
Với $$a,b$$ là các số thực dương, $m,n$ tùy ý, ta có:
>[!formula] Các tính chất của lũy thừa với số mũ thực
>$$a^m . a^n = a^{m+n}$$
>$$\frac{a^m}{a^n} = a^{m-n}$$
>$$(a^m)^n = a^{m.n}$$
>$$(ab)^m = a^m . b^m$$
>$$m>1: a^m > b^m \Leftrightarrow a > b$$
>$$m<1: a^m > b^m \Leftrightarrow a < b$$

## Logarit
>[!formula] Định nghĩa
>$a,b$ là các thực dương, $m$ được gọi là **logarit cơ số a của b** nếu:
>$$a^m = b$$
>Kí hiệu: $$m = \log_{a}{b}$$
>Không có logarit của 0 hoặc số âm

>[!formula] Một số tính chất
>$$\log_a{1} = 0$$
>$$\log_a{a} = 1$$
>$$a^{\log_a{b}} = b$$
>$$\log_a{a^b} = b$$

## Quy tắc tính logarit
>[!formula] Các quy tắc
>$$\log_a{m.n} = \log_a{m} + \log_a{n}$$
>$$\log_a{\frac{m}{n}} = \log_a{m} - \log_a{n}$$
>$$\log_a{\frac{1}{m}} = - \log_a{m}$$
>$$\log_a{m^n} = n \log_a{m}$$
>$$\log_a{\sqrt[n]{b}} = \frac{1}{n} \log_a{b}$$
>$$\log_a{b} = \frac{\log_c{b}}{\log_c{a}}$$
>$$\log_a{b} = \frac{1}{\log_b{a}}$$
>$$\log_{a^m}{b} = \frac{1}{m}. \log_a{b}$$

%%Sửa đổi vào 10:30:58 Ngày 01 tháng 07 năm 2023%%

## Hàm số lũy thừa $y = x^a$
- Tập xác định:
	- $a$ nguyên dương: $\mathbb{R}$
	- $a$ nguyên không dương: $\mathbb{R} \setminus \{0\}$
	- $a$ không nguyên: $(0;+\infty)$
- Đạo hàm:
$$(x^a)' = a.x^{a-1}$$
$$[(u(x))^a]' = a.u^{a-1}(x).u'(x)$$

## Hàm số mũ $y = a^x$
- Tập xác định: $\mathbb{R}$
- Đạo hàm:
$$(e^x)' = e^x$$
$$(e^{u(x)}) = e^{u(x)}.u'(x)$$
$$(a^x)' = a^x.\ln{a}$$
$$(a^{u(x)})' = a^{u(x)}.\ln{a}.u'(x)$$

## Hàm số logarith $y = \log_a{x}(a>0,a\neq 1)$
- Tập xác định: $(0;+\infty)$
- Đạo hàm:
$$(\log_a{x})' = \frac{1}{x \ln{a}}$$
$$(\log_a{u(x)})' = \frac{u'(x)}{u(x) \ln{a}}$$


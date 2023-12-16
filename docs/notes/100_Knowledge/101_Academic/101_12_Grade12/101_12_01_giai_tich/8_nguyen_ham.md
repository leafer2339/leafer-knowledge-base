---
tags:
  - academic
subject: calculus
chapter: 3
unit: 8
title: Nguyên hàm
share: true
---


Môn: [Giải tích 12](./101_12_01_giai_tich.md)

# Nguyên hàm

## Nguyên hàm và tính chất

>[!formula] Định nghĩa
>Cho hàm số $f(x)$ xác định trên $K$. Hàm số $F(x)$ được gọi là **nguyên hàm** của $f(x)$ trên $K$ nếu
>$$F'(x) = f(x) \forall x \in K$$
>Mọi hàm số liên tục trên $K$ đều có nguyên hàm trên $K$

Với $F(x)$ là nguyên hàm của $f(x)$ trên $K$ thì $F(x) + C; \;  C \in \mathbb{R}$ là **họ các nguyên hàm** của $f(x)$ trên $K$. 
>[!formula] Kí hiệu nguyên hàm
>$$\int{f(x)\,\mathrm{d}x} = F(x) + C$$


Từ định nghĩa, ta có:
>[!formula] Tính chất 1
>$$\int{f'(x)\,\mathrm{d}x} = f(x) + C$$

Xét: 
$$(k.F(x))' = k.F'(x) = k.f(x)$$
Tức là
$$\int{kf(x)\,\mathrm{d}x} = k.F(x) +C  = k.(F(x) + C_1)= k.\int{f(x)\,\mathrm{d}x}$$
>[!formula] Tính chất 2
>$$\int{kf(x)} = k.\int{f(x)}$$

Xét hai hàm số $F(x)$ và $G(x)$ với $F'(x) = f(x)$ và $G'(x) = g(x)$. Ta có:
$$(F(x) \pm G(x))' = F'(x) \pm G'(x) = f(x) \pm g(x)$$
Từ đó:
$$\int [f(x) \pm g(x)] \, \mathrm{d}x = F(x) \pm G(x) + C = (F(x) + C_1) \pm (G(x) + C_2) = \int{f(x)\,\mathrm{d}x} \pm \int{g(x)\,\mathrm{d}x}$$
>[!formula] Tính chất 3
>$$\int{f(x) \pm g(x)} = \int{f(x)} \pm \int{g(x)}$$

## Phương pháp tính nguyên hàm
Xét hàm số $f(u)$ có nguyên hàm $F(u) + C$. $u = u(x)$ là hàm số có đạo hàm liên tục 
Theo công thức [đạo hàm](derivative.md) của hàm hợp, ta có:
$$F(u(x))' = F'(u(x)).u'(x) = f(u(x)).u'(x)$$
>[!formula] Phương pháp đổi biến số
>$$\int{f(u(x)).u'(x)\mathrm{d}x} = F(u(x)) + C$$

Hệ quả:
$$\int{f(ax+b)\,\mathrm{d}x} = \frac{1}{a}F(ax+b) + C$$
Xét hai hàm số $u(x)$ và $v(x)$ có đạo hàm liên tục trên $K$
Theo công thức đạo hàm của tích:
$$[u(x).v(x)]' = u'(x)v(x) + u(x)v'(x)$$
Hay
$$u(x).v'(x) = [u(x).v(x)]' - u'(x)v(x)$$
Lấy nguyên hàm hai vế ta có:
>[!formula] Phương pháp tính nguyên hàm từng phần:
>$$\int{u(x).v'(x) \mathrm{d}x} = u(x)v(x) - \int{u'(x)v(x)\mathrm{d}x}$$

## Một số công thức nguyên hàm thường gặp
$$\int 0 \, \mathrm{d}x = C$$
$$\int \mathrm{d}x =x+C$$
$$\int x^\alpha\,\mathrm{d}x = \frac{1}{\alpha + 1} x ^ {\alpha + 1} + C \; (\alpha \neq -1)$$
$$\int \frac{1}{x}\,\mathrm{d}x = \ln{|x|} + C$$
$$\int e^x\,\mathrm{d}x = e^x + C$$
$$\int a^x\, \mathrm{d}x = \frac{a^x}{\ln{a}} + C \;(a>0;a\neq 1)$$
$$\int \cos{x} \, \mathrm{d}x = \sin{x} + C$$
$$\int \sin{x} \, \mathrm{d}x = - \cos{x} + C$$
$$\int \frac{1}{\cos^2{x}}\, \mathrm{d}x = \tan{x} + C$$
$$\int \frac{1}{\sin^2{x}}\,\mathrm{d}x = \cot{x} + C$$

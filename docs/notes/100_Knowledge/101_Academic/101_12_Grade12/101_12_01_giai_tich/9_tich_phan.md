---
tags:
  - academic
  - subject/maths/calculus
subject: calculus
chapter: 3
unit: 9
title: Tích phân
share: true
---





- [Bài trước](./8_nguyen_ham.md)


Môn: [Giải tích 12](./101_12_01_giai_tich.md)

# Tích phân
## Định nghĩa

>[!formula] Định nghĩa
>Cho $f(x)$ là một hàm số liên tục trên $[a;b]$, Với $F(x)$ là một [nguyên hàm](./8_nguyen_ham.md) của $f(x)$ trên $[a;b]$.
>Hiệu $F(b) - F(a)$ được gọi là **tích phân** từ $a$ đến $b$ (**tích phân xác định** trên $[a;b]$) của $f(x)$
>$$\int_a^b{f(x)\mathrm{d}x} = F(x)\big|_a^b = F(b) - F(a)$$ 

Với:
- $\int_a^b$ được gọi là **dấu tích phân**
- $a$: **cận dưới**
- $b$: **cận trên**
- $f(x)$: **hàm số** dưới dấu tích phân
- $f(x)\mathrm{d}x$: **biểu thức** dưới dấu tích phân

>[!caution] Lưu ý:
>Giá trị của tích phân chỉ phụ thuộc vào hàm số dưới dấu tích phân và hai cận, không liên quan đến biến

## Một số tính chất và quy ước

> [!formula]
> 
> $$\int_a^a{f(x)\mathrm{d}x} = 0$$
> $$\int_a^b{f(x)\mathrm{d}x} = - \int_b^a{f(x)\mathrm{d}x}$$
> $$\int_a^b{k.f(x)\mathrm{d}x} = k.\int_a^b{f(x)\mathrm{d}x}$$
> $$\int_a^b{[f(x)\pm g(x)]\mathrm{d}x} = \int_a^b{f(x)\mathrm{d}x} \pm \int_a^b{g(x)\mathrm{d}x}$$
> $$\int_a^b{f(x)\mathrm{d}x} = \int_c^b{f(x)\mathrm{d}x} + \int_a^c{f(x)\mathrm{d}x}$$

## Phương pháp tính tích phân

>[!formula] Phương pháp đổi biến
>Phương pháp chung:
>- Chọn một biến số khác, xác lập hàm giữa biến số ban đầu so với biến số mới hoặc ngược lại
>- Thay đổi cận để phù hợp với biến mới
>- Biến đổi biểu thức nằm dưới dấu tích phân phù hợp với biến mới
>- Dạng 1:
>Cho $f(x)$ liên tục trên $[a;b]$. Xét hàm số $x = \varphi(t)$ có đạo hàm liên tục trên $[\alpha,\beta]$ sao cho $\varphi(\alpha) = a$ và $\varphi(\beta) = b$ và $a \le \varphi(t) \le b \forall t \in [\alpha, \beta]$. Khi đó ta có:
>$$\int_a^b{f(x)\mathrm{d}x} = \int_\alpha^\beta{f(\varphi(t))\varphi'(t).\mathrm{d}t}$$
>- Dạng 2:
>Cho $f(x)$ liên tục trên $[a;b]$ và hàm số $u = u(x)$ có đạo hàm liên tục trên $[a;b]$.
>Nếu có thể viết:
>$$f(x) = g(u(x)).u'(x)$$
>Thì 
>$$\int_a^b{f(x)} = \int_{u(a)}^{u(b)}{g(u).\mathrm{d}u}$$

>[!formula] Phương pháp tính tích phân từng phần
>Cho hai hàm số $u=u(x)$ và $v=v(x)$ có đạo hàm liên tục trên $[a;b]$ thì:
>$$\int_a^b{ u(x).v'(x) \mathrm{d} x } = [u(x).v(x)]\bigg|_a^b - \int_a^b{ v(x).u'(x) \mathrm{d} x}$$

## Một số kết quả

- Hàm số $f(x)$ liên tục trên $[-a;a]$. Ta có:
$$\int_{-a}^{a}{ f(x) \mathrm{d} x } = \cases{ 2.\int_{0}^{a}{f(x)\mathrm{d} x} \text{   nếu f(x) là hàm chẵn} \\ 0 \text{   nếu f(x) là hàm lẻ }} $$

- Với $f(x)$ liên tục trên $[a;b]$ :
$$\int_0^{\frac{\pi}{2}}{f(\sin x)\mathrm{d}x} = \int_0^{\frac{\pi}{2}}{f(\cos x)}\mathrm{d}x$$
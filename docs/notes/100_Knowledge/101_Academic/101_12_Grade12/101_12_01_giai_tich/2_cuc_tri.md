---
tags:
  - academic
subject: calculus
chapter: 1
unit: 2
title: Cực trị của hàm số
share: true
---



Tạo mới vào lúc 21:55:03 vào Ngày 12 tháng 06 năm 2023

# Cực trị của hàm số

>[!note] Tổng quan
>Môn: [Giải tích 12](./101_12_01_giai_tich.md)

## Cực trị là cái gì
>[!formula] Định nghĩa cực trị
>Cho hàm số $f(x)$ xác định và liên tục trên $(a;b)$, $x_0 \in (a;b)$:
>- Nếu tồn tại $h>0$ sao cho $f(x)<f(x_0)$ với mọi $x \in (x_0-h;x_0+h), x\neq x_0$ thì ta nói $f(x)$ đạt **cực đại** tại $x_0$
>- Nếu tồn tại $h>0$ sao cho $f(x)<f(x_0)$ với mọi $x \in (x_0-h;x_0+h), x \neq x_0$ thì ta nói $f(x)$ đạt **cục tiểu** tại $x_0$

- Khi đó, giá trị $x_0$ được gọi là **điểm cực đại (cực tiểu)** của hàm số, kí hiệu $x_{CĐ}$, $x_{CT}$
- Giá trị $f(x_0)$ được gọi là **giá trị cực đại (cực tiểu)** của hàm số, kí hiệu $f_{CĐ}$, $f_{CT}$

## Điều kiện để hàm số có cực trị
### Điều kiện cần

>[!formula] Định lí
>Nếu $f(x)$ đạt cực trị tại $x_0$ và có đạo hàm tại $x_0$ thì $f'(x_0) = 0$

Chứng minh?: Xét $f(x)$ có cực đại tại $x_0$, cực tiểu chứng minh tương tự
Do $f(x)$ có đạo hàm tạo $x_0$ nên

$$f'(x_0) = f'({x_0}^+) = f'({x_0}^-)$$

$$f'({x_0}^+) = \lim_{\Delta x \rightarrow 0^+}{\frac{f(x_0 + \Delta x ) - f(x_0)}{\Delta x}}$$

Do $f(x)$ có cực đại tại $x_0$ nên $f(x_0 + \Delta x) < f(x_0)$, từ đó

$$\frac{f(x_0 + \Delta x ) - f(x_0)}{\Delta x} < 0$$ 

với $\Delta x >0$

Ta có:

$$f'({x_0}^+) = \lim_{\Delta x \rightarrow 0}{\frac{f(x_0 + \Delta x ) - f(x_0)}{\Delta x}} \le 0$$

$$f'({x_0}^-) = \lim_{\Delta x \rightarrow 0^-}{\frac{f(x_0 + \Delta x ) - f(x_0)}{\Delta x}}$$

Do $f(x)$ có cực đại tại $x_0$ nên $f(x_0 + \Delta x) < f(x_0)$, từ đó

$$\frac{f(x_0 + \Delta x ) - f(x_0)}{\Delta x} > 0$$ với $\Delta x >0$

$$f'({x_0}^+) = \lim_{\Delta x \rightarrow 0}{\frac{f(x_0 + \Delta x ) - f(x_0)}{\Delta x}} \ge 0$$

Để $f'(x_0) = f'({x_0}^+) = f'({x_0}^-)$ thì $f'(x_0)  = f'({x_0}^+) = f'({x_0}^-)=0$ (đpcm)

### Điều kiện đủ

>[!formula] Định lí
>Hàm số $y=f(x)$ liên tục trên $K = (a;b)$, có đạo hàm trên $K$ hoặc $K\setminus \{x_0\}$ với $x_0 \in K$
>- Nếu $f'(x) > 0$ trên $(a;x_0)$ và $f'(x)<0$ trên $(x_0;b)$ thì $x_0$ là một điểm cực đại của $f(x)$
>- Nếu $f'(x) < 0$ trên $(a;x_0)$ và $f'(x)>0$ trên $(x_0;b)$ thì $x_0$ là một điểm cực tiểu của $f(x)$

## Quy tắc


- [Bài sau](./3_gtnn_gtln.md)


- [Bài trước](./1_tinh_don_dieu.md)

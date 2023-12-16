---
tags:
  - academic
subject: physics
chapter: 1
unit: 5
title: Tổng hợp dao động
share: true
---



- [Bài sau](./VL1206%20-%20S%C3%B3ng.md)


- [Bài trước](./VL1204%20-%20Dao%20%C4%91%E1%BB%99ng%20t%E1%BA%AFt%20d%E1%BA%A7n%20v%C3%A0%20dao%20%C4%91%E1%BB%99ng%20c%C6%B0%E1%BB%A1ng%20b%E1%BB%A9c.md)


# Tổng hợp hai dao động cùng phương, cùng tần số
Cho hai [dao động điều hòa](./VL1201%20-%20Dao%20%C4%91%E1%BB%99ng%20%C4%91i%E1%BB%81u%20h%C3%B2a.md):
$$x_1 = A_1.\cos(\omega.t + \varphi_1)$$
$$x_2 = A_2.\cos(\omega.t + \varphi_2)$$
## I. Độ lệch pha
- Gọi $\Delta \varphi = \varphi_1 - \varphi_2$ là **độ lệch pha** của hai dao động:
	- Nếu $\Delta \varphi <0$ hay $\varphi_1 < \varphi_2$, ta nói $x_1$ _trễ pha_ hơn $x_2$
	- Nếu $\Delta \varphi > 0$ hay $\varphi_1 > \varphi_2$, ta nói $x_1$ _sớm pha_ hơn $x_2$
- Các trường hợp đặc biệt:
	- $\Delta \varphi = k2\pi (k\in Z)$ ta nói $x_1$ và $x_2$ _cùng pha_, khi đó ta luôn có: ^cung-pha
		- $$\frac{x_1}{x_2} = \frac{A_1}{A_2}$$
	- $\Delta \varphi = \pi + k2\pi (k \in Z)$ ta nói $x_1$ và $x_2$ _ngược pha_, khi đó ta luôn có:
		- $$\frac{x_1}{x_2} = -\frac{A_1}{A_2}$$
	- $\Delta \varphi = \frac{\pi}{2} + k2\pi(k \in Z)$ ta nói $x_1$ và $x_2$ _vuông pha_, khi đó ta luôn có:
		- $$(\frac{x_1}{A_1})^2 + (\frac{x_2}{A_2})^2 =1$$

## II. Tổng hợp hai dao động theo phương pháp giản đồ Fre-nen
Ta có thể biểu diễn các dao động dưới dạng các _vector quay_ trên đường tròn lượng giác, việc tổng hợp dao động sẽ là phép cộng các vector quay
$x = x_1 + x_2$
$\vec{A} = \vec{A_1} + \vec{A_2}$
Khi đó ta có:
$x = A.\cos{(\omega.t+ \varphi)}$
Trong đó:
$$A^2 = {A_1}^2 + {A_2}^2 + 2A_1A_2\cos{\Delta \varphi}$$
$$tan\varphi = \frac{A_1\sin{\varphi_1}+ A_2\sin{\varphi_2}}{A_1\cos{\varphi_1}+A_2\cos{\varphi_2}}$$
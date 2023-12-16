---
tags:
  - academic
subject: physics
chapter: 1
unit: 1
title: Dao động điều hòa
share: true
---


- [Bài sau](./VL1202%20-%20Con%20l%E1%BA%AFc%20l%C3%B2%20xo.md)




# Dao động điều hòa
## I. Định nghĩa
**Dao động cơ** là chuyển động của một vật _qua lại_ một vị trí xác định, được gọi là **vị trí cân bằng**
Dao động cơ được gọi là **tuần hoàn** nếu sau những khoảng thời gian _bằng nhau_, vật trở lại _vị trí cũ_ theo _hướng cũ_.
Dao động điều hòa là dạng cơ bản nhất của dao động tuần hoàn.

>[!notes] Định nghĩa
>Dao động điều hòa là dao động trong đó li độ của vật là _hàm cos (hoặc sin)_ của thời gian

## II. Phương trình của dao động
### Phương trình li độ

>[!formula] Phương trình dao động điều hòa
>$$x = A.\cos{(\omega.t+\varphi)}$$



### Phương trình vận tốc
Vận tốc là [đạo hàm](derivative.md) của li độ

>[!formula] Phương trình vận tốc của dao động điều hòa
>$$v = -A.\omega.\sin{(\omega.t+\varphi)}$$
>



### Phương trình gia tốc
Gia tốc là đạo hàm của vận tốc, hay đạo hàm cấp hai của li độ.

>[!formula] Phương trình gia tốc của dao động điều hòa
>$$a = -A.\omega^2.\cos{(\omega.t+\varphi)}=-\omega^2.x$$

## III. Các đại lượng liên quan
- A là **biên độ** của vật. Đây là độ lệch _lớn nhất_ của vật so với vị trí cân bằng. $A > 0$, thường là hằng số trong các dao động.
$x_{max} = A$,$x_{min} =-A$

- $\phi = \omega.t+\varphi$ được gọi là **pha** của dao động _tại thời điểm t_. **Pha** được dùng để xác định _vị trí_ và _hướng_ dao động của vật
- $\varphi$ là pha của dao động tại t=0, còn được gọi là **pha ban đầu** $-\pi \le\varphi \le \pi$
- $\omega$ là **tần số góc** của dao động, thường lấy đơn vị rad/s.

- Sau một khoảng thời gian xác định không đổi, vật trở về vị trí cũ theo hướng cũ, thời gian này được gọi là **chu kì**.
>[!notes] Định nghĩa
>- Chu kì là khoảng thời gian vật thực hiện được một _dao động toàn phần_
>- Tần số là _số dao động toàn phần_ thực hiện trong một _đơn vị thời gian_(thường là giây)

- Chu kì thường được kí hiệu là T, tần số là f. Ta có các mối liên hệ sau:
>[!formula] Công thức liên hệ giữa chu kì, tần số và tần số góc
>$$f = \frac{1}{T}$$
>$$\omega = \frac{2\pi}{T} = 2\pi.f$$

Đơn vị theo hệ SI: T: s, f:Hz, $\omega$:rad/s

## IV. Các điểm đặc biệt
- Biên là 2 điểm xa vị trí cân bằng nhất trong chuyển động của vật
$|x| = x_{max} = A$
- Điểm có $x = A$ được gọi là **biên dương**, còn điểm có $x = -A$ được gọi là **biên âm**.
- **Vị trí cân bằng** là điểm có $x=0$, tại đây vật coi như không có lực tác dụng và chuyển động thẳng đều
- 
|Đại lượng|Biên|Vị trí cân bằng|
|---|---|---|
|$\phi$|- Biên dương: 0 <br> - Biên âm: $\pi$|$\pm \frac{\pi}{2}$|
|$x$|- Biên dương: A <br> - Biên âm: -A|0|
|$v$|= 0|cực đại <br> $v=v_{max} = \omega.A$|
|$a$|- Biên dương: cực đại <br>$a=a_{max} = \omega^2.A$|= 0|

## V. Các công thức nâng cao

>[!formula] Công thức độc lập thời gian
>$$(\frac{x}{A})^2 + (\frac{v}{v_{max}})^2 = 1$$
>$$x^2 + (\frac{v}{\omega})^2 = A^2$$
>$$|v| = \omega \sqrt{A^2-x^2}$$
>$$\omega = \frac{\sqrt{{v_2}^2-{v_1}^2}}{\sqrt{{x_1}^2-{x_2}^2}}$$

>[!formula] Thời gian vật chuyển động từ $x_1$ đến $x_2$:
>$\cos{\phi_1} = \frac{x_1}{A}$, $\cos{\phi_2} = \frac{x_2}{A}$
>$$\Delta t = \frac{\phi_2-\phi_1}{\omega}$$

Các khoảng thời gian đặc biệt:
![dddh_time.excalidraw](dddh_time.excalidraw.md)

>[!formula] Quãng đường trong khoảng thời gian $\Delta t$
>Góc quét $\alpha = \omega . \Delta t = n\pi + \alpha\prime (0<\alpha\prime<\pi)$
>$$S = n.2A + S(\alpha\prime)$$
>$S(\alpha\prime)$ được tính bằng cách xét vị trí điểm trên đường tròn lượng giác

![dddh_s.excalidraw](dddh_s.excalidraw.md)

>[!formula] Quãng đường nhỏ nhất, lớn nhất
>$$S_{max}(\alpha\prime) = 2A\sin{\frac{\alpha\prime}{2}}$$
>$$S_{min}(\alpha\prime) = 2A(1-\cos{\frac{\alpha\prime}{2}})$$



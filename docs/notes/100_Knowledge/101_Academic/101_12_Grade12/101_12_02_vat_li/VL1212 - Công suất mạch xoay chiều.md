---
tags:
  - academic
subject: physics
chapter: 3
unit: 12
title: Công suất của mạch điện xoay chiều
status: finished
share: true
---



- [Bài sau](./VL1214%20-%20M%C3%A1y%20bi%E1%BA%BFn%20%C3%A1p%20M%C3%A1y%20ph%C3%A1t%20%C4%91i%E1%BB%87n%20v%C3%A0%20%C4%90%E1%BB%99ng%20c%C6%A1%20%C4%91i%E1%BB%87n.md)


- [Bài trước](./VL1211%20-%20M%E1%BA%A1ch%20c%C3%B3%20R%20L%20C%20m%E1%BA%AFc%20n%E1%BB%91i%20ti%E1%BA%BFp.md)


# Công suất của mạch điện xoay chiều
Xét mạch điện xoay chiều có:
- Điện áp tức thời $u = U\sqrt{2}\cos{\omega.t}$
- Cường độ tức thời $i = I\sqrt{2}\cos{(\omega.t + \varphi)}$
Ta sẽ có công suất tức thời tại thời điểm t là:
$$p = u.i = 2.U.I.\cos{(\omega.t)}\cos{(\omega.t+\varphi)}$$
$$p = U.I[\cos{\varphi}+ \cos{(2\omega.t+\varphi)}]$$
Công suất trung bình trong 1 chu kì:
$$P = \bar{p} = \frac{\int_{0}^{T} U.I.[\cos{\varphi} + \cos{(2\omega.t + \varphi)}]\,dt}{T}$$
$$P = U.I.\cos{\varphi} + \frac{\int_0^T \cos{(2.\omega.t+\varphi)} \, dt}{T}$$
Đặt $u(t)= 2\omega.t + \varphi$ ta có:
$$\int_0^T \cos(2\omega.t + \varphi)\,dt = \frac{1}{2\omega} \int_0^{4\pi} \cos(u)\,du = \sin{x}{\big |}_{0}^{4\pi}  = 0$$

>[!formula] Công thức công suất của mạch xoay chiều
>$$P = U.I.cos\varphi$$

$\cos{\varphi}$ được gọi là **hệ số công suất**
Trong [mạch có R,L,C mắc nối tiếp](./VL1211%20-%20M%E1%BA%A1ch%20c%C3%B3%20R%20L%20C%20m%E1%BA%AFc%20n%E1%BB%91i%20ti%E1%BA%BFp.md), ta có
$$\cos{\varphi} = \frac{U_R}{U} = \frac{R}{Z} $$
Từ đó ta có:
$$P = U.\frac{U}{Z}.\frac{R}{Z} = R.\frac{U^2}{Z^2} = I^2.R$$
>[!formula] Công suất của mạch điện gồm R,L,C mắc nối tiếp:
>$$P = I^2.R$$
>Bằng với công suất tỏa nhiệt của R
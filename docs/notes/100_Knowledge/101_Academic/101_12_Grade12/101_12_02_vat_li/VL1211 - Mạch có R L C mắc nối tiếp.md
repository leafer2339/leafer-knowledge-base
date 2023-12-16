---
tags:
  - academic
subject: physics
chapter: 3
unit: 11
title: Mạch có R,L,C mắc nối tiếp
share: true
---



- [Bài sau](./VL1212%20-%20C%C3%B4ng%20su%E1%BA%A5t%20m%E1%BA%A1ch%20xoay%20chi%E1%BB%81u.md)


- [Bài trước](./VL1210%20-%20D%C3%B2ng%20%C4%91i%E1%BB%87n%20xoay%20chi%E1%BB%81u.md)


%%Tạo mới vào lúc 08:43:08 vào Ngày 28 tháng 06 năm 2023%%

# Mạch có R,L,C mắc nối tiếp
## Định luật về điện áp tức thời

>[!formula] Định luật
>TRong mạch xoay chiều gồm nhiều đoạn mạch mắc nối tiếp, điện áp tức thời giữa hai đầu mạch bằng _tổng đại số_ các điện áp tức thời giữa hai đầu của từng đoạn mạch

## Định luật Ôm cho đoạn mạch có R, L, C mắc nối tiếp
![Excalidraw/rlc.excalidraw](rlc.excalidraw.md)
Ta có:
$$\vec{U} = \vec{U_R} + \vec{U_L} + \vec{U_C} = \vec{U} + \vec{U_{LC}}$$
Theo [phương pháp giản đồ Fre-nen](academic/lop12/vat_li/tong_hop_dao_dong.md#II.%20Tổng%20hợp%20hai%20dao%20động%20theo%20phương%20pháp%20giản%20đồ%20Fre-nen) ta có:
$$U^2 = {U_R}^2 + {U_{LC}}^2$$
Trong đó: $U_{LC} = |U_L - U_C|$
Từ đó ta có:
>[!formula] Định luật Ôm cho đoạn mạch có R, L, C mắc nối tiếp
> $$U^2 = I^2[R^2 + (Z_L - Z_C)^2]$$
> $$I = \frac{U}{\sqrt{R^2 + (Z_L - Z_C)^2}}$$
> Đặt $Z = \sqrt{R^2 + (Z_L - Z_C)^2}$, đại lượng này được gọi là **tổng trở** của mạch

## Độ lệch pha giữa điện áp và cường độ dòng điện
Ta có:
>[!formula] Độ lệch pha giữa u và i
>$$\tan{\varphi} = \frac{U_L - U_C}{U_R} = \frac{Z_L - Z_C}{R}$$

## Cộng hưởng điện
Khi $Z_L = Z_C$, điện áp tổng hợp sẽ _cùng pha_ với cường độ dòng điện. Lúc này $Z=R$, đây được gọi là hiện tượng **cộng hưởng điện**.
>[!formula] Điều kiện cho cộng hưởng điện
>$$Z_L = Z_C \Leftrightarrow \omega . L = \frac{1}{\omega . C} \Leftrightarrow \omega^2 .L.C = 1$$
>Khi đó I lớn nhất $I = \frac{U}{R}$
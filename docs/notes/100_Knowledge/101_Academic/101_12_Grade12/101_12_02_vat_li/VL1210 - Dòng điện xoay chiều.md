---
tags:
  - academic
subject: physics
chapter: 3
unit: 10
title: Dòng điện xoay chiều
share: true
---



- [Bài sau](./VL1211%20-%20M%E1%BA%A1ch%20c%C3%B3%20R%20L%20C%20m%E1%BA%AFc%20n%E1%BB%91i%20ti%E1%BA%BFp.md)


- [Bài trước](./VL1209%20-%20S%C3%B3ng%20%C3%A2m.md)


%%Tạo mới vào lúc 22:08:37 vào Ngày 19 tháng 06 năm 2023%%


# Dòng điện xoay chiều
## I. Đại cương
### Định nghĩa
>[!notes] Định nghĩa
>**Dòng điện xoay chiều (hình sin)** là dòng diện có cường độ _biến thiên tuần hoàn_ theo thời gian với quy luật của hàm số sin hay cos, tổng quát:
>$$i = I_0 \cos{(\omega t + \varphi)}$$

Dòng điện xoay chiều được tạo ra khi cho một vòng dây khép kín quay quanh trục cố định trong cùng mặt phẳng với cuộn dây đặt trong từ trường đều. Dòng điện sinh là là [dòng điện cảm ứng](academic/lop11/physic/notes/grade11/chapter5/ch5_u19_cam_ung_dien_tu.md). Theo đó, suất điện động cảm ứng là đối của đạo hàm của từ thông theo thời gian:
$$e = - \Phi'$$
Với $$\Phi = NBS\cos\alpha = NBS\cos{(\omega t + \varphi)}$$
$$e = \omega NBS \sin\alpha$$
$$i = \frac{e}{R} = \frac{\omega NBS}{R} \sin\alpha$$

>[!formula] Lưu ý
>Vậy dòng diện cảm ứng như trên là một dòng điện xoay chiều có biên độ $$I_0 = \frac{\omega NBS}{R}$$

### Giá trị hiệu dụng

>[!notes] Định nghĩa
>Giá trị hiệu dụng của một đại lượng có giá trị bằng giá trị của đại lượng đó của dòng điện không đổi sao cho công suất tiêu thụ của hai dòng điện là như nhau

Công suất trong dòng điện xoay chiều biến thiên tuần hoàn theo thời gian:
$$p = Ri^2 = R.I_0^2 \cos^2{\omega t}$$
Giá trị trung bình của công suất:
$$\bar{p} = P = \frac{1}{2} R.I_0^2$$
Với $I$ là giá trị hiệu dụng, ta có:
$$P = R.I^2 = \frac{1}{2} R. I_0^2 \Leftrightarrow I = \frac{I_0}{\sqrt{2}}$$
Như vậy

>[!formula] Giá trị hiệu dụng
>Giá trị hiệu dụng = Giá trị cực đại  / $\sqrt{2}$

Nếu cường độ dòng điện biến thiên tuần hoàn theo chu kì T, điện áp cũng vậy, tức là, nếu $i = I_0 \cos{(\omega .t)} = I.\sqrt{2} \cos{(\omega.t)}$ thì $u = U_0 \cos{(\omega.t + \varphi)} = U \sqrt{2} \cos{\omega.t + \varphi}$
## II. Mạch điện xoay chiều chỉ có điện trở
Khi nối hai đầu của mạch chỉ gồm điện trở vào điện áp xoay chiều $u = U \sqrt{2}\cos{(\omega.t)}$ ta có cường độ dòng điện xoay chiều:
$$i = \frac{u}{R} = \frac{U}{R} \sqrt{2} \cos{(\omega.t)} = I \sqrt{2} \cos{(\omega.t)}$$

Vậy
>[!formula] Định luật Ôm đối với mạch điện xoay chiều thuần điện trở
>$$I = \frac{U}{R}$$
>Cường độ dòng diện hiệu dụng có giá trị bằng thương điện áp hiệu dụng và điện trở của mạch

## III. Mạch điện xoay chiều chỉ có tụ điện
Khi nối hai đầu của mạch chỉ có tụ điện vào điện áp xoay chiều $u = U \sqrt{2} \cos{\omega.t}$
Cường độ dòng điện, theo định nghĩa, là đạo hàm của lượng điện tích dịch chuyển theo thời gian:
$$i = q' = (C.u)' = (C.U.\sqrt{2} \cos{\omega t}) = -\omega C.U.\sqrt{2} \sin{\omega.t} = \omega.C.U \sqrt{2} \cos{(\omega.t + \frac{\pi}{2})}$$

Từ đó ta có:
- Cường độ dòng điện _sớm pha_ $\frac{\pi}{2}$ so với điện áp. Ngược lại, điện áp _trễ pha_ $\frac{\pi}{2}$ so với cường độ dòng điện
- Cường độ dòng điện hiệu dụng $I = \omega.C.U$

Đặt $Z_C = \frac{1}{\omega.C}$. Đại lượng này gọi là **dung kháng** của mạch (đơn vị: $\ohm$)
Ta có $I = \frac{U}{Z_C}$
Từ đó:

>[!formula] Định luật Ôm đối với mạch chứa tụ điện
>$$I = \frac{U}{Z_C} = \omega.C.U$$
>$$Z_C = \frac{1}{\omega.C}$$
>Cường độ dòng điện hiệu dụng có giá trị bằng thương điện áp hiệu dụng và dung kháng của mạch

- Dung kháng làm cho $i$ sớm pha hơn $u$ một góc $\frac{\pi}{2}$

>[!formula] Dung kháng của mạch gồm nhiều tụ điện mắc nối tiếp:
>$$Z_C = \frac{1}{C_1\omega} + \frac{1}{C_2\omega} + ... + \frac{1}{C_n \omega}$$


## III. Mạch điện xoay chiều chỉ có cuộn cảm thuần
Đặt hai đầu một cuộn cảm độ tự cảm $L$ vào điện áp xoay chiều $u$. Dòng điện chạy qua cuộn cảm
$$i = I \sqrt{2} \cos{(\omega.t)}$$
Khi đó, do [hiện tượng tự cảm](academic/lop11/physic/notes/grade11/chapter5/ch5_u20_tu_cam.md), xuất hiện một xuất điện động chống lại sự biến thiên của dòng điện, hay, ngược chiều dòng điện.
Từ đó ta có $u = i.r - e$
Với cuộn cảm thuần, tức là $r = 0$ ta có: $u = -e = L.i'(t)$
Từ đó:
$$u = -L.\omega.I.\sqrt{2} \sin{(\omega.t)} = L . \omega.I \sqrt{2} \cos{(\omega.t + \frac{\pi}{2})}$$

Vậy điện áp hiệu dụng $U = \omega.L.I$
Nếu đặt $Z_L = \omega.L$, đại lượng này gọi là **cảm kháng** của mạch, ta có:
$$I = \frac{I}{Z_L}$$
Ngoài ra, điện áp _sớm pha_ $\frac{\pi}{2}$ so với cường độ dòng điện hoặc cương đồ dòng điện _trễ pha_ $\frac{\pi}{2}$ so với điện áp 

>[!formula] Định luật Ôm cho đoạn mạch chỉ có cuộn cảm thuần
>$$I = \frac{U}{\omega.L} = \frac{U}{Z_L}$$
>$$Z_L = \omega.L$$

Cảm kháng làm cho $u$ sớm pha $\frac{\pi}{2}$ so với $i$.

>[!formula] Cảm kháng của mạch gồm nhiều cuộn cảm mắc nối tiếp
> $$Z_L = (L_1+L_2+...+L_n).\omega$$

%%Sửa đổi vào 09:06:20 Ngày 23 tháng 06 năm 2023%%


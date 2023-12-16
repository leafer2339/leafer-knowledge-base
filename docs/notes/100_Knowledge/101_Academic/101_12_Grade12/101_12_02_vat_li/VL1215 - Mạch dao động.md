---
tags:
  - academic
subject: physics
chapter: 4
unit: 14
title: Mạch dao động
status: finished
share: true
---



- [Bài sau](./VL1216%20-%20%C4%90i%E1%BB%87n%20t%E1%BB%AB%20tr%C6%B0%E1%BB%9Dng.md)


- [Bài trước](./VL1214%20-%20M%C3%A1y%20bi%E1%BA%BFn%20%C3%A1p%20M%C3%A1y%20ph%C3%A1t%20%C4%91i%E1%BB%87n%20v%C3%A0%20%C4%90%E1%BB%99ng%20c%C6%A1%20%C4%91i%E1%BB%87n.md)

# I. Mạch dao động

>[!formula] Định nghĩa
>![../../../../500_Media/Excalidraw/mach_dao_dong.excalidraw](mach_dao_dong.excalidraw.md)
>- Một cuộn cảm thuần mắc với một tụ điện thành một mạch điện kín gọi là **mạch dao động**
>- **Mạch dao động lí tưởng** là mạch có điện trở gần như bằng 0

- Mạch dao động hoạt động khi ta tích điện cho tụ điện rồi cho nó phóng điện trong mạch. Tụ điện phóng điện qua lại, tạo ra dòng điện xoay chiều
- Để sử dụng, ta nối hai hai bản của tụ điện với mạch ngoài

## II. Dao động điện từ tự do trong mạch dao động
>[!formula] Định nghĩa
>**Dao động điện từ tự do** trong mạch dao động là sự biến thiên điều hòa theo thời gian của điện tích $q$ của tụ điện, cường độ dòng điện $i$,...

![mach_dao_dong_hoat_dong.excalidraw](mach_dao_dong_hoat_dong.excalidraw.md)

Hiệu điện thế giữa hai đầu mạch:
$$u = e - i.r$$
Với mạch lí tưởng, $r \approx 0$ , ta có: 
$$u = e = -L.i'$$
(Xem thêm [Suất điện động tự cảm](ch5_u20_tu_cam.md#III.%20Suất%20điện%20động%20tự%20cảm))
Ta cũng có, đối với tụ điện:
$$q = C.u$$
Vậy $$q = -L.C.i'$$
mà $i = q'$ nên:
$$q = -L.C.q''$$
Từ đó ta có [phương trình vi phân](phuong_trinh_vi_phan.md):
$$q'' + \frac{q}{LC} = 0$$
Giải phương trình đó, ta có phương trình của $q$:
$$q = q_0.cos(\omega.t + \varphi)$$
$$\omega = \frac{1}{\sqrt{LC}}$$
Từ đó ta có phương trình của i:
$$i = \frac{\mathrm{d}q}{\mathrm{d}t} = q_0.\omega.cos(\omega.t+ \varphi + \frac{\pi}{2})$$
Chọn $t = 0$ là thời điểm tụ điện bắt đầu phóng điện:
$$q = q_0 = E.C ;\quad i = 0; \quad \varphi = 0$$
>[!formula] Tính chất
>Điện tích $q$ của một bản tụ điện và cường độ dòng điện $i$ dao động biến thiên điều hòa với tần số góc $\omega = \frac{1}{\sqrt{L.C}}$, trong đó $i$ sớm pha hơn $q$ một góc $\frac{\pi}{2}$

Từ đó ta có, chu kì và tần số của dao động tự do, còn gọi là **chu kì và tần số dao động riêng của mạch dao động**:
>[!formula] Chu kì và tần số riêng của mạch dao động
> $$T = \frac{2\pi}{\omega} = 2\pi\sqrt{LC}\quad ; \quad f = \frac{1}{2\pi\sqrt{LC}}$$

Ngoài ra, cảm ứng từ B tỉ lệ thuận với cường độ dòng điện i và điện trường E tỉ lệ thuận với điện tích q

# III. Năng lượng điện từ
- Khi tụ điện được tích điện, trong tụ có [năng lượng điện trường](ch1_u6_tu_dien.md)
$$W_C = \frac{q^2}{2.C}= \frac{1}{2}.C.u^2$$
- Khi có dòng điện chạy trong cuộn cảm, cuộn dây có [năng lượng từ trường](ch5_u20_tu_cam.md)
$$W_L = \frac{1}{2}.L.i^2$$
- Từ đó, trong mạch có **năng lượng điện từ**, là tổng năng lượng điện trường và năng lượng từ trường
>[!formula] Năng lượng điện từ
>$$W = W_C + W_L = \frac{1}{2}.C.u^2 + \frac{1}{2}.L.i^2$$
- Nếu không có tiêu hao năng lượng, năng lượng điện từ được **bảo toàn**, giá trị này là một _hằng số_:
$$W = \max{W_C} = \max{W_L} = \frac{q_0^2}{2C}$$

---
tags:
  - academic
subject: physics
chapter: 3
unit: 13
title: Máy biến áp và Máy phát điện
status: finished
share: true
---



- [Bài sau](./VL1215%20-%20M%E1%BA%A1ch%20dao%20%C4%91%E1%BB%99ng.md)

- [Bài trước](./VL1212%20-%20C%C3%B4ng%20su%E1%BA%A5t%20m%E1%BA%A1ch%20xoay%20chi%E1%BB%81u.md)


# I. Máy biến áp và Máy phát điện
## Máy biến áp
### Nhu cầu biến đổi điện áp
Từ các nhà máy điện, công suất phát điện truyền đi được tính theo công thức
$$P_{\text{phát}} = U_{\text{phát}}.I$$
Trong quá trình truyền tải sẽ có hao phí do tỏa nhiệt:
$$Q = I^2.r = {\frac{P_p^2}{U_p^2}} . r$$
Như vậy, để giảm hao phí, các tốt nhất là tăng điện áp. Tuy nhiên sau đó cần giảm điện áp để có thể sử dụng, từ đó máy biến áp sinh ra để thực hiện quá trình này
### Cấu tạo máy biến áp
Máy biến áp cơ bản gồm:
- Lõi biến áp (lõi từ): làm bằng sắt non pha sillic, thường gồm các lá kim loại xếp chồng lên nhau, có tẩm cách điện giữa các lớp.
- 2 cuộn dây: cuộn dây sơ cấp gồm $N_{sc}$ vòng, nhận điện vào và cuộn thứ cấp với $N_{tc}$ vòng để truyền điện ra

![may_bien_ap.excalidraw](may_bien_ap.excalidraw.md)
### Nguyên tắc hoạt động của máy biến áp
Khi có dòng xoay chiều qua cuộn sơ cấp, một từ thông được tạo ra trong lõi biến áp, truyền qua cuộn thứ cấp. Các đường sức từ đi qua hai cuộn dây là như nhau. Gọi từ thông qua một vòng dây là $\Phi = \Phi_0\cos{\omega.t}$
Từ thông qua cuộn sơ cấp và thứ cấp lần lượt là:
$$\Phi_{sc} = N_{sc}\Phi_0\cos{\omega.t}$$
$$\Phi_{tc} = N_{tc}\Phi_0\cos{\omega.t}$$
Trong cuộn thứ cấp lúc này xuất hiện xuất điện động xoay chiều:
$$e_{tc} = -\Phi'_{tc} = \omega.N_{tc}\Phi_0\sin{\omega.t}$$
Như vậy, dòng điện xuất hiện trong cuộn thứ cấp có _cùng tần số_ với dòng điện trong cuộn sơ cấp
Thực nghiệm cho thấy:
$$\frac{U_{tc}}{U_{sc}} = \frac{N_{tc}}{N_{sc}} = \frac{I_{sc}}{I_{tc}}$$
Điều này cho phép công suất điện được bảo toàn trong quá trình biến đổi (với điều kiện lí tượng: điện năng không bị hao hụt)

## 2. Máy phát điện xoay chiều
### Máy phát điện xoay chiều một pha
MPĐ xoay chiều một pha có 2 bộ phận chính:
- Roto (phần cảm): là một vành tròn gắn 2p cực nam châm: p nam, p bắc, quay quanh một trục với tần số n vòng/giây
- Stato (phần ứng): các cuộn dây giống nhau trên một vòng tròn
Khi roto xoay bên trong stato, từ thông qua các cuộn dây trong stato biến thiên tuần hoàn với tần số $$f=p.n$$
Từ đó sinh ra một suất điện động xoay chiều cùng tần số, sinh ra dòng điện xoay chiều 
![../../../../500_Media/Excalidraw/mpdxc1p.excalidraw](mpdxc1p.excalidraw.md)

### Máy phát điện xoay chiều ba pha
![../../../../500_Media/Excalidraw/mpdxc3p.excalidraw](mpdxc3p.excalidraw.md)
- MPĐ xoay chiều ba pha là máy tạo ra _3 suất điện động xoay chiều_ hình sin có cùng tần số, cùng biên độ, lệch pha nhau một góc $\frac{2\pi}{3}$
- Cấu tạo:
	- Stato: Ba cuộn dây hình trụ giống nhau gắn cố định trên một vành tròn tại 3 vị trí đối xứng, lệch nhau $120 \degree$, 3 trục đồng quy tại tâm O của đường tròn
	- Roto: Một nam châm NS có thể quay quanh trục O.
- Nguyên lí:
	- Khi nam châm quay quanh O, từ thông qua các cuộn dây là 3 hàm số sin của thời gian, có cùng tần số, cùng biên độ nhưng lệch nhau các góc $\frac{2\pi}{3}$
	- Từ đó, trong các cuộn dây xuất hiện các [dòng điện cảm ứng](ch5_u19_cam_ung_dien_tu.md) có cùng tần số, cùng biên độ nhưng lệch nhau $\frac{2\pi}{3}$
- Cách mắc mạch ba pha:
	- Máy phát ba pha được nối với ba mạch tiêu thụ, giả thiết là như nhau (cùng [điện trở](./VL1210%20-%20D%C3%B2ng%20%C4%91i%E1%BB%87n%20xoay%20chi%E1%BB%81u.md#II.%20Mạch%20điện%20xoay%20chiều%20chỉ%20có%20điện%20trở), [dung kháng](./VL1210%20-%20D%C3%B2ng%20%C4%91i%E1%BB%87n%20xoay%20chi%E1%BB%81u.md#III.%20Mạch%20điện%20xoay%20chiều%20chỉ%20có%20tụ%20điện), [cảm kháng](./VL1210%20-%20D%C3%B2ng%20%C4%91i%E1%BB%87n%20xoay%20chi%E1%BB%81u.md#III.%20Mạch%20điện%20xoay%20chiều%20chỉ%20có%20cuộn%20cảm%20thuần)), gọi là các tải _đối xứng_
	- Có hai cách mắc tải:
		- Hình sao:
		![../../../../500_Media/Excalidraw/mac_ba_pha_sao.excalidraw](mac_ba_pha_sao.excalidraw.md)
		- Hình tam giác
		![../../../../500_Media/Excalidraw/mac_ba_pha_tam_giac.excalidraw](mac_ba_pha_tam_giac.excalidraw.md)
- $u_{1O}, u_{2O},u_{3O}$ được gọi là **điện áp pha**
- $u_{12},u_{23},u_{31}$ được gọi là **điện áp dây**

>[!formula] Hệ thức giữa điện áp hiệu dụng:
> $$U_{\text{dây}} = \sqrt{3}.U_{\text{pha}}$$

>[!formula]- Chứng minh:
>Do 3 điện áp pha cùng biên độ, cùng tần số nhưng lệch pha nhau $\frac{2\pi}{3}$, đặt:
>$$u_{1O} = u_0\cos{(\omega.t)}$$
>$$u_{2O} = u_0\cos{\bigg(\omega.t + \frac{2\pi}{3}\bigg)}$$
>Ta có:
>$$u_{12} = u_{1O} + u_{O2} = u_{1O} - u_{2O} = u_0\cos{(\omega.t)} - u_0\cos{\bigg(\omega.t + \frac{2\pi}{3}\bigg)} = -2u_0.\sin{\bigg( \omega.t + \frac{\pi}{3}\bigg)}.\sin{\frac{\pi}{3}}$$
>$$u_{12} = \sqrt{3}u_0\cos{\bigg(\omega.t + \frac{5\pi}{6}\bigg)}$$
>$$\Rightarrow U_{12} = \sqrt{3} U_{1O}$$

- Ưu điểm của dòng ba pha:
	- Tiết kiệm dây dẫn hơn dòng một pha
	- Cung cấp điện cho các động cơ ba pha dùng trong nhà máy, xí nghiệp

## 3. Động cơ không đồng bộ ba pha
### Động cơ không đồng bộ
- Sắp xếp cơ cấu như sau:
![dong_co_khong_dong_bo.excalidraw](dong_co_khong_dong_bo.excalidraw.md)
- Bên trong Nam châm N-S có một từ trường với cảm ứng từ $\vec{B}$. Ban đầu, ta đặt khung dây có vectơ pháp tuyến $\vec{n}$ cùng phương với cảm ứng từ $\vec{B}$
- Khi nam châm quay với tốc độ góc $\omega$, từ thông qua khung dây giảm do góc giữa $\vec{B}$ và $\vec{n}$ tăng dần, điều này tạo ra một [dòng điện xoay chiều](ch5_u19_cam_ung_dien_tu.md) trong khung dây.
- Khung dây chứa dòng điện nằm trong từ trường khiến cho khung quay bên trong nam châm. Theo [định luật Lenz](ch5_u19_cam_ung_dien_tu.md#III.%20Định%20luật%20Lenz%20về%20chiều%20dòng%20điện%20cảm%20ứng), dòng điện cảm ứng bên trong khung dây sẽ có tác dụng chống lại chiều biến thiên từ thông, tức là thu hẹp góc giữa $\vec{B}$ và $\vec{n}$, khung dây sẽ quay _cùng chiều_ với nam châm.
- Khung dây quay nhanh dần, khiến cho độ biến thiên từ thông qua khung dây giảm dần, làm giảm cường độ dòng điện cảm ứng và lực từ
- Khi mô-men ngẫu lực từ cân bằng với mô-men ngẫu lực của lực cản và ma sát, khung dây quay đều với tốc độ góc nhỏ hơn tốc độ góc của nam châm
### Động cơ không đồng bộ ba pha
#### Cấu tạo
- Rô-to: khung dây dẫn. Để tăng hiệu quả khung dây được ghép thành một lồng hình trụ (rô-to lồng sóc):
![../../../../500_Media/Pasted image 20230813211622.png](../../../../../attachment/Pasted%20image%2020230813211622.png)
- Sta-to: gồm 3 cuộn dây giống nhau, đặt đối xứng, lệch nhau 120 độ. 3 cuộn dây này được truyền dòng điện 3 pha từ máy phát điện xoay chiều 3 pha, tạo ra 3 từ trường. Từ trường tổng hợp của 3 từ trường này là một **từ trường quay**, đóng vai trò của nam châm quay
![dong_co_khong_dong_bo_ba_pha.excalidraw](dong_co_khong_dong_bo_ba_pha.excalidraw.md)
Theo nguyên lí của động cơ không đồng bộ, rô-to sẽ quay đều.
---
share: true
title: Một số bài toán về mạch điện xoay chiều
---

# Một số bài toán về mạch điện xoay chiều

## Bài toán cực trị

### Trường hợp R biến thiên

Công suất của mạch:
$$P = I^2.R = \frac{U^2}{Z^2}.R$$
$$P = \frac{U^2}{R^2 + (Z_L - Z_C)^2}.R$$

Ta có:
$$R^2 + (Z_L - Z_C)^2 \ge 2R.|Z_L-Z_C|$$

Như vậy
$$P \le \frac{U^2.R}{2R|Z_L - Z_C|} = \frac{U^2}{2|Z_L - Z_C|}$$

Dấu "=" xảy ra khi $R = |Z_L - Z_C|$

>[!formula] Công suất cực đại khi R thay đổi
>Khi R thay đổi, công suất đạt cực đại khi $$R = R_0 = |Z_L - Z_C|$$. Giá trị cực đại này là $$P_{max} = \frac{U^2}{2|Z_L - Z_C|}$$


### Trường hợp L, C hoặc $\omega$ biến thiên

- Cường độ dòng điện hiệu dụng của mạch đạt cực đại khi xảy ra [cộng hưởng](./VL1211%20-%20M%E1%BA%A1ch%20c%C3%B3%20R%20L%20C%20m%E1%BA%AFc%20n%E1%BB%91i%20ti%E1%BA%BFp.md#Cộng%20hưởng%20điện), khi đó:

$$\omega^2 . L . C = 1$$
$$I_{max} = \frac{U}{R}$$

- Lúc này, hiệu điện thế qua các linh kiện không đổi và công suất của mạch cũng đạt cực đại
- Hệ quả: $u$ và $i$ cùng pha với nhau, khi đó $u$ vuông pha $u_L$ và $u$ vuông qua với $u_C$
- Công suất của mạch lúc này:

$$P_{max} = \frac{U^2}{R}$$

- Khi thay đổi giá trị của L, C hoặc $\omega$, công suất cũng thay đổi:

$$P = P_{max} . \cos^2{\varphi}$$

- Khi L biến thiên, xét $u_L$

$$U_L = \frac{U}{Z}. Z_L = \frac{U}{\sqrt{R^2 + (Z_L - Z_C)^2}}.Z_L$$

$$U_L = \frac{U}{\sqrt{\frac{R^2 + Z_C^2}{Z_L^2} - \frac{2Z_C}{Z_L} + 1 }}$$

$$U_L$$ sẽ đạt cực đại khi $$\frac{R^2 + Z_C^2}{Z_L^2} - \frac{2Z_C}{Z_L} + 1 $$ đạt cực tiểu, xảy ra khi $$\frac{1}{Z_L} = \frac{Z_C}{R^2+ Z_C^2} \Leftrightarrow Z_L = Z_{L0} = \frac{R^2 + Z_C^2}{Z_C}$$
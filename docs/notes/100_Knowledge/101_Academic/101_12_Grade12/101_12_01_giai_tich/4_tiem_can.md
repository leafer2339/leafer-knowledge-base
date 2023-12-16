---
tags:
  - academic
subject: calculus
chapter: 1
unit: 4
title: Tiệm cận
share: true
---



%%Tạo mới vào lúc 07:54:18 vào Ngày 19 tháng 06 năm 2023%%

# Đường tiệm cận

>[!note] Tổng quan
>Môn: [Giải tích 12](./101_12_01_giai_tich.md)

## Tiệm cận ngang
>[!formula] Định nghĩa
>Hàm số $y = f(x)$ xác định trên một khoảng vô hạn. Đường thẳng $y = y_0$ được gọi là **đường tiệm cận ngang** của đồ thị hàm số $y =f(x)$ nếu một trong hai điều kiện sau được thỏa mãn:
>$$\lim_{x \rightarrow + \infty}{f(x)} = y_0$$
>$$\lim_{x \rightarrow - \infty}{f(x)} = y_0$$

## Tiệm cận đứng
>[!formula] Định nghĩa
>Đường thẳng $x = x_0$ được gọi là **đường tiệm cận đứng** của đồ thị hàm số $y=f(x)$ nếu ít nhất một trong các điều kiện sau được thỏa mãn:
>$$\lim_{x \rightarrow x_0^+}{f(x)} = +\infty$$
>$$\lim_{x \rightarrow x_0^+}{f(x)} = -\infty$$
>$$\lim_{x \rightarrow x_0^-}{f(x)} = +\infty$$
>$$\lim_{x \rightarrow x_0^-}{f(x)} = -\infty$$

## Tiệm cận xiên
>[!formula] Định nghĩa
>Đường thẳng $y = ax+b$ được gọi là **đường tiệm cận xiên** của đồ thị hàm số $y =f(x)$ nếu một trong hai điều kiện sau thỏa mãn:
>$$\lim_{x\rightarrow + \infty} {f(x)-(ax+b)} = 0$$
>$$\lim_{x\rightarrow - \infty} {f(x)-(ax+b)} = 0$$

Tính nhanh:
$$a = \lim_{x\rightarrow \infty}{\frac{f(x)}{x}}$$
$$b = \lim_{x\rightarrow \infty}{f(x)-ax}$$
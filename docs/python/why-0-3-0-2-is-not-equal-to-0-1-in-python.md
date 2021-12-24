# 为什么 Python 中 0.3–0.2 不等于 0.1？

> 原文:[https://www . geesforgeks . org/why-0-3-0-2-不等于 0-1-in-python/](https://www.geeksforgeeks.org/why-0-3-0-2-is-not-equal-to-0-1-in-python/)

在本文中，我们将看到为什么 Python 中的 0.3–0.2 不等于 0.1。背后的原因是被称为“精度”，这是因为计算机不是用十进制计算，而是用二进制计算。计算机不使用基数为 10 的系统，而是使用基数为 2 的系统(也称为二进制代码)。

下面是实现。

## 蟒 3

```
# code
print(0.3 - 0.2)
print(0.3 - 0.2 == 0.1)
```

**输出**

```
0.09999999999999998
False

```
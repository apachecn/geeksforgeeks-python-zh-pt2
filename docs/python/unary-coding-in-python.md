# Python 中的一元编码

> 原文:[https://www.geeksforgeeks.org/unary-coding-in-python/](https://www.geeksforgeeks.org/unary-coding-in-python/)

**一元码**有时也叫**温度计码**是熵编码的一种。这是一种无损数据压缩技术，应用于 Golomb 码。

自然数 *n* 的一元表示是 n 个 1 后跟一个 0。例如，6 的一元代码将是 6 个 1 后跟一个 0，即 1111110

**示例:**

```
Input: 5
Output: 111110
result has 5 ones followed by a 0 

Input: 1
Output: 10
result has 1 one followed by a 0
```

**进场:**

*   **对于编码:**取一个空列表，然后在最后追加 N 次 1 和 0，然后将其转换为字符串并打印结果。
*   **解码:**取一个给定的字符串，数 1，然后打印结果。

**例 1:** 自然数的一元表示。

## 蟒蛇 3

```
# Unary code encoding
N = 8
A = []

for i in range(N):
    A.append(1)

A.append(0)

B = [str(k) for k in A]

C = "".join(B)

print("Unary code for", N,
      'is', C)
```

**输出:**

```
Unary code for 8 is 111111110
```

**示例 2:** 一元代码的十进制表示。

## 蟒蛇 3

```
# Unary code decoding

code =  "111111110"
count = 0

for i in code:
    if i == "1":
        count += 1

print("decoded number is :", count)
```

**输出:**

```
decoded number is : 8
```
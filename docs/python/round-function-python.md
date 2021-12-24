# Python 中的 round()函数

> 原文:[https://www.geeksforgeeks.org/round-function-python/](https://www.geeksforgeeks.org/round-function-python/)

**Python round()函数 float** 点数从十进制值到最接近的 10 的倍数。

int 值为 10 的最接近倍数的次方减去 ndigits，其中 ndigits 为小数点后的精度。**如果两个倍数相等，则四舍五入到偶数。**

### **Python round()语法:**

> 四舍五入(数字、位数)

### **Python 圆()参数:**

> *   **Number:** The number to be rounded.
> *   **Number of digits (optional):** The number of digits to which a given number is rounded.

如果第二个参数是**缺少**，那么 round()函数**返回**:

1.  如果只给定一个整数，例如 15，那么它本身就会舍入到 15。
2.  如果给定了一个十进制数，那么它将舍入到最接近 10 的倍数，即幂减 ndigits

## Python round()示例:

### 示例 1:如果缺少第二个参数，Python round()函数

## 蟒蛇 3

```py
# for integers
print(round(15))

# for floating point
print(round(51.6))
print(round(51.5))
print(round(51.4))
```

**输出:**

```py
15
52
52
51
```

当第二个参数为**出现**时，则**返回:**

当第(ndigit+1)位> =5 时，舍入到的最后一个十进制数字增加 1，否则保持不变。

### 示例 2:如果第二个参数存在，Python round()函数

## 蟒蛇 3

```py
# when the (ndigit+1)th digit is =5
print(round(2.665, 2))

# when the (ndigit+1)th digit is >=5
print(round(2.676, 2))

# when the (ndigit+1)th digit is <5
print(round(2.673, 2))
```

**输出:**

```py
2.67
2.68
2.67
```

### 示例 3: Python 舍入()

## 蟒蛇 3

```py
print(round(12))
print(round(12.7))
```

**输出:**

```py
12
13
```

### 示例 4: Python 向下舍入()

## 蟒蛇 3

```py
print(round(12))
print(round(12.1))
print(round(12.4))
print(round(12.5))
```

**输出:**

```py
12
12
12
12
```

## **错误和异常**

类型错误:当参数中除了数字之外还有其他任何东西时，会引发此错误。

## 蟒蛇 3

```py
print(round("a", 2))
```

**输出:**

```py
Runtime Errors:
Traceback (most recent call last):
  File "/home/ccdcfc451ab046030492e0e758d42461.py", line 1, in 
    print(round("a", 2))  
TypeError: type str doesn't define __round__ method
```

## **实际应用:**

函数舍入的一个常见用途是处理分数和小数之间的不匹配。

舍入数字的一个用途是在将 1/3 转换为十进制时，将小数点右边的三个都缩短。大多数情况下，当您需要处理十进制中的 1/3 时，您会使用四舍五入的数字 0.33 或 0.333。事实上，当小数中没有精确的分数时，你通常只使用小数点右边的两三个数字。你如何用十进制表示 1/6？记得围捕！

## 蟒蛇 3

```py
# practical application
b = 1/3
print(b)
print(round(b, 2))
```

**输出:**

```py
0.3333333333333333
0.33
```

**注意:**在 python 中，如果我们将数字舍入到 floor 或 ceil 而不给出第二个参数，例如它将返回 15.0，在 Python 3 中它将返回 15，因此为了避免这种情况，我们可以在 Python 中使用(int)类型转换。还需要注意的是，round()函数在求两个数的平均值时表现出不同寻常的行为。
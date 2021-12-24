# Python 数学函数–next after()

> 原文:[https://www . geesforgeks . org/python-math-function-next after/](https://www.geeksforgeeks.org/python-math-function-nextafter/)

**math.nextafter()** 是 python 3.9.0 中引入的一个函数。nextafter(x，y)返回 x 之后朝向 y 的下一个浮点值，如果 x 等于 y，则返回 y。

> **语法:** math.nextafter(x，y)
> 
> **参数:**
> 
> x 和 y 是两个整数/浮点值。
> 
> **返回:**
> 
> 向 y 返回 x 之后的下一个浮点值。如果 x 等于 y，则返回 y

**例 1:** math.nextafter(x，math.inf)向上:朝向正无穷大。

## 蟒蛇 3

```py
import math

print(math.nextafter(2, math.inf))
```

**输出:**

```py
2.0000000000000004

```

**例 2:** math.nextafter(x，-math.inf)向下:朝向负无穷大。

## 蟒蛇 3

```py
import math

print(math.nextafter(2, -math.inf))
```

**输出:**

```py
1.9999999999999998

```

**例 3:** math.nextafter(x，0.0)趋近于零。

## 蟒蛇 3

```py
import math

print(math.nextafter(2, 0.0))
```

**输出:**

```py
2.0000000000000004

```
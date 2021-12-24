# Python 数学库| isclose()方法

> 原文:[https://www . geesforgeks . org/python-math-library-is close-method/](https://www.geeksforgeeks.org/python-math-library-isclose-method/)

在 Python 数学模块中， **`math.isclose()`** 方法用于判断两个浮点数的值是否接近。要使用该功能，您必须导入**数学**模块。

> **语法:**无符号(a，b，rel_tol = 1e-09，abs_tol 0.0)
> 
> **参数:**
> **rel_tol:** 被认为“接近”的最大差值，相对于输入值的大小
> **abs_tol:** 被认为“接近”的最大差值，与输入值的大小无关
> 
> -> `**rel_tol**`和`**abs_tol**` 可以通过使用关键字参数进行更改，也可以根据它们在参数列表中的位置直接提供 as。
> 
> **返回值:**如果 a 的值接近 b，则返回真，否则返回假。

**注意:**对于被认为接近的值，它们之间的差值必须小于至少一个公差。

**代码#1:**

```
# Importing Math module
import math

# printing whether two values are close or not
print(math.isclose(2.005, 2.005))
print(math.isclose(2.005, 2.004))
print(math.isclose(2.006, 2.005))
```

**输出:**

```
True
False
False

```

**代码#2:**

```
# Importing Math module
import math

# printing whether two values are close or not
print(math.isclose(2.005, 2.125, abs_tol = 0.25))
print(math.isclose(2.547, 2.0048, abs_tol = 0.5))
print(math.isclose(2.0214, 2.00214, abs_tol = 0.02))
```

**输出:**

```
True
False
True

```

您可以更改绝对公差，因为在上述情况下，绝对公差在所有三种情况下都不同。

**参考:** [Python 数学库](https://docs.python.org/3/library/math.html)
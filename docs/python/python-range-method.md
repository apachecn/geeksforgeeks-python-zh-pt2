# Python 范围()方法

> 原文:[https://www.geeksforgeeks.org/python-range-method/](https://www.geeksforgeeks.org/python-range-method/)

Python 中有许多可选项，如列表、元组等。 **range()** 给出了另一种使用一些条件来初始化数字序列的方法。
**range()** 常用于 for 循环，因此，在处理任何类型的 Python 代码时，相同的知识都是关键方面。

> **语法:**范围(开始、停止、步进)
> **参数:**
> **开始:**构建序列必须从其开始的元素。(默认值:0)
> **停止:**顺序中的数字必须结束的元素编号(不包括)。
> **步骤:**可以是+ve 或-ve 数，表示填充列表时需要跳过的元素。(默认值:1)
> **返回:**使用公式的列表:
> 列表[n] =开始+步骤*n(对于正步骤和负步骤)其中，n > =0，列表[n] = 0，列表[n] >停止(对于负步骤)
> 如果步骤为 0，则返回值错误。步骤中检查值约束，不满足返回空序列，否则根据公式返回序列。

**代码#1 :** 演示范围()无步长参数

## 蟒蛇 3

```
# Python3 code to demonstrate the
# working of range() without step

# using range()
lis1 = list(range(6))
lis2 = list(range(3, 6))
lis3 = list(range(-6, 2))

# initializing list using range, 1 parameter
# only stop parameter
print("List generated using 1 parameter : " + str(lis1))

# initializing list using range, 2 parameters
# only step and stop parameters
print("List generated using 2 parameters : " + str(lis2))

# initializing list using range, 2 parameter
# only step and stop parameters
print("List generated using 2 parameters with negatives : " + str(lis3))
```

**输出:**

```
List generated using 1 parameter : [0, 1, 2, 3, 4, 5]
List generated using 2 parameters : [3, 4, 5]
List generated using 2 parameters with negatives : [-6, -5, -4, -3, -2, -1, 0, 1]
```

**代码#2 :** 使用步骤
演示射程()

## 蟒蛇 3

```
# Python 3 code to demonstrate the
# working of range() with step

# initializing list using range
# using step
print("List generated using step : " +
    str(list(range(3, 10, 2))))

# initializing list using range
# using negative step
print("List generated using negative step : " +
                  str(list(range(10, -5, -3))))

# initializing list using range
# using negative step,
# value constraints fail case
print("List generated using step, value constraints fail : " +
                                 str(list(range(10, -5, 3))))

# initializing list using range
# using 0 step
# error
print("List generated using 0 step : " +
              str(list(range(3, 7, 0))))
```

**输出:**

```
List generated using step : [3, 5, 7, 9]
List generated using negative step : [10, 7, 4, 1, -2]
List generated using step, value constraints fail : []
```

例外:

```
Traceback (most recent call last):
  File "/home/bdae725dff7b38d3681eee38f6a6d434.py", line 23, in 
    print("List generated using 0 step : " + str(list(range(3, 7, 0))))
ValueError: range() arg 3 must not be zero
```
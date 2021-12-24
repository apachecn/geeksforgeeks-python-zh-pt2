# Python 中的旋转矩阵模块

> 原文:[https://www . geesforgeks . org/rotate-matrix-module-in-python/](https://www.geeksforgeeks.org/rotate-matrix-module-in-python/)

**旋转矩阵**是一个有趣的新 python 模块，它允许将矩阵(二维数组)转换为顺时针旋转或逆时针旋转。目前只有两种方法。你可以通过这些方法循环旋转 n 次。

### 装置

该模块不是 python 内置的，但可以使用以下命令安装:

```py
pip install rotate-matrix
```

### 功能

**1)顺时针()**:显然顾名思义，这个函数是用来顺时针旋转矩阵的。

> **语法:**顺时针(矩阵)
> 
> **参数:**以矩阵为参数，类型列表。
> 
> **返回值:**传递矩阵的时钟旋转版本

**示例:**

## 蟒蛇 3

```py
import rotate_matrix

mat = [[5, 2, 6], [8, 2, 9], [3, 6, 7], [3, 6, 2]]

print(rotate_matrix.clockwise(mat))
```

**输出**:

> [(6, 9, 7, 2), (2, 2, 6, 6), (5, 8, 3, 3)]

**2)逆时针():**此模块的此功能逆时针旋转给定矩阵。

> **语法:**逆时针(矩阵)
> 
> **参数:**以矩阵为参数，类型列表
> 
> 返回值:传递矩阵的逆时针旋转版本

**示例:**

## 蟒蛇 3

```py
import rotate_matrix

mat = [[5, 2, 6], [8, 2, 9], [3, 6, 7], [3, 6, 2]]

print(rotate_matrix.anti_clockwise(mat))
```

**输出**:

> [(3, 3, 8, 5), (6, 6, 2, 2), (2, 7, 9, 6)]
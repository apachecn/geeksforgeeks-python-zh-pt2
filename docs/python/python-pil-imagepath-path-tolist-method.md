# 蟒蛇 PIL | ImagePath。Path.tolist()方法

> 原文:[https://www . geesforgeks . org/python-pil-imagepath-path-to list-method/](https://www.geeksforgeeks.org/python-pil-imagepath-path-tolist-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。 **`ImagePath`** 模块用于存储和操作二维矢量数据。路径对象可以传递给`ImageDraw`模块上的方法。

**`ImagePath.Path.tolist()`** 将路径转换为 Python 列表[(x，y)，…]。

> **语法:** PIL。ImagePath.Path.tolist(平面=0)
> 
> **参数:**
> 
> **flat**–默认情况下，这个函数返回一个 2 元组的列表[(x，y)，…]。如果该参数为真，它将返回一个平面列表[x，y，…]。
> 
> **返回:**坐标列表。

```py

# from PIL importing ImagePath
from PIL import ImagePath

# creating a list to map
getbox = list(zip(range(3, 41, 1), range(11, 22, 2)))
result = ImagePath.Path(getbox)

# using tolist function
a = result.tolist()
print(getbox)
print(a)
```

**输出:**

> [(3，11)，(4，13)，(5，15)，(6，17)，(7，19)，(8，21)]
> [(3.0，11.0)，(4.0，13.0)，(5.0，15.0)，(6.0，17.0)，(7.0，19.0)，(8.0，21.0)]

**另一个例子:**改变参数。

```py

# from PIL importing ImagePath
from PIL import ImagePath

# creating a list to map
getbox = list(zip(range(5, 51, 16), range(15, 22, 4)))
result = ImagePath.Path(getbox)

# using tolist function
a = result.tolist()
print(getbox)
print(a)
```

**输出:**

> [(5，15)，(21，19)]
> [(5.0，15.0)，(21.0，19.0)]
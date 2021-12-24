# 蟒蛇 PIL | ImagePath。Path.map()方法

> 原文:[https://www . geesforgeks . org/python-pil-imagepath-path-map-method/](https://www.geeksforgeeks.org/python-pil-imagepath-path-map-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。 **`ImagePath`** 模块用于存储和操作二维矢量数据。路径对象可以传递给`ImageDraw`模块上的方法。

**`ImagePath.Path.map()`** 通过函数映射路径。

> **语法:** ImagePath。Path.map(函数)
> 
> **参数:**
> **参数**-创建列表。
> **范围**–分配范围。
> 
> **返回:** (x0，y0)

```

# from PIL importing ImagePath
from PIL import ImagePath

# creating a list to map
getbox = list(zip(range(3, 41, 1), range(11, 22, 2)))
result = ImagePath.Path(getbox)

# using map function
b = result.map(lambda x, y: (x + 2, y + 2))
a = result.tolist()
print(a)
```

**输出:**

> [(5.0, 13.0), (6.0, 15.0), (7.0, 17.0), (8.0, 19.0), (9.0, 21.0), (10.0, 23.0)]

**另一个例子:**改变参数。

```

# from PIL importing ImagePath
from PIL import ImagePath

# creating a list to map
getbox = list(zip(range(3, 41, 1), range(11, 22, 2)))
result = ImagePath.Path(getbox)

# using map function
b = result.map(lambda x, y: (x + 12, y + 12))
a = result.tolist()
print(a)
```

**输出:**

> [(15.0, 23.0), (16.0, 25.0), (17.0, 27.0), (18.0, 29.0), (19.0, 31.0), (20.0, 33.0)]
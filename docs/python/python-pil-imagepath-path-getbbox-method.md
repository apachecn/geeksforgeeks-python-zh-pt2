# Python PIL | ImagePath。Path.getbbox()方法

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-pil-imagepath-getbbox-method/

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。 **`ImagePath`** 模块用于存储和操作二维矢量数据。路径对象可以传递给`ImageDraw`模块上的方法。

**`ImagePath.Path.getbbox()`** 获取路径的包围盒。

> **语法:** ImagePath。Path.getbbox()
> 
> **参数:**
> **参数**-创建 getbox 列表。
> **范围**–分配范围。
> 
> **返回:** (x0，y0，x1，y1)

```

# importing image class from PIL package
import math
from PIL import ImagePath

# creating a list to getbox 
getbox = list(zip(range(2, 51, 5), range(14, 25, 5)))
result = ImagePath.Path(getbox).getbbox()
print(result)
print(getbox)
```

**输出:**

```
(2.0, 14.0, 12.0, 24.0)
[(2, 14), (7, 19), (12, 24)]

```

**另一个例子:**改变参数。

```

# importing image class from PIL package
import math
from PIL import ImagePath

# creating a list to getbox 
getbox = list(zip(range(3, 41, 1), range(11, 22, 2)))
result = ImagePath.Path(getbox).getbbox()
print(result)
print(getbox)
```

**输出:**

```
(3.0, 11.0, 8.0, 21.0)
[(3, 11), (4, 13), (5, 15), (6, 17), (7, 19), (8, 21)]

```
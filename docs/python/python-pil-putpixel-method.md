# Python PIL | putpixel()方法

> 原文:[https://www.geeksforgeeks.org/python-pil-putpixel-method/](https://www.geeksforgeeks.org/python-pil-putpixel-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。像素访问类提供对 PIL 的读写访问。像素级的图像数据。
访问单个像素相当慢。如果你正在循环一个图像中的所有像素，可能有一个更快的方法使用枕头应用编程接口的其他部分。

**putpixel()** 修改 x，y 处的像素。对于单波段图像，颜色作为单个数值给出，对于多波段图像，颜色作为元组给出

> **语法:** putpixel(self，xy，color)
> 
> **参数:**
> 
> **xy :** 像素坐标，给定为(x，y)
> **值:**–像素值。
> 
> **返回:**有像素的图像。

**所用图像:**
![](img/b676bf4e5579500345ba1e2db94e0f29.png)

```

# Importing Image from PIL package 
from PIL import Image

# creating a image object
image = Image.open(r'C:\Users\System-Pc\Desktop\python.png') 

width, height = image.size

for x in range(height):
    image.putpixel( (x, x), (0, 0, 0, 255) )

image.show()
```

**输出:**
![](img/c33818aa3b9dc1a8f61930748113e08c.png)

**另一个例子:**这里我们改变颜色参数。
**图像使用**
![](img/221cf0797de804ae1930e49085a2072a.png)

```
# Importing Image from PIL package 
from PIL import Image

# creating a image object
image = Image.open(r'C:\Users\System-Pc\Desktop\ybear.jpg') 

width, height = image.size

for x in range(height):
    image.putpixel( (x, x), (10, 10, 10, 255) )

image.show()
```

**输出:**
![](img/3eba704f549ebc5eebbc99df1e7e2651.png)
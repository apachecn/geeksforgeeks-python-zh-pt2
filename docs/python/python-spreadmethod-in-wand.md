# Python–魔杖中的 spread()方法

> 原文:[https://www.geeksforgeeks.org/python-spreadmethod-in-wand/](https://www.geeksforgeeks.org/python-spreadmethod-in-wand/)

**扩散**用附近找到的随机像素值替换每个像素。**扩散()**功能用于对图像应用扩散效果。可以通过定义半径来控制搜索新像素的区域大小。

> **语法:**
> 
> ```
> wand.image.spread(radius, method)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 半径 | 数字。真实的 | 像素与源的距离。默认值为 0.0，这将允许 ImageMagick 自动选择半径。 |
> | 方法 | 基绳 | 插值方法。仅适用于 ImageMagick-7。可选参数。 |

**来源影像:**
![](img/379843214f773be60d93005bc813b0f8.png)

**例 1:**

```
# Import Image from wand.image module
from wand.image import Image

# Read image using Image() function
with Image(filename ="koala.jpeg") as img:

    # Generate spread image using spread() function
    img.spread(radius = 8.0)
    img.save(filename ="spreadkoala.jpg")
```

**输出:**
![](img/2ca1a10b8962b534d55a21e9680671ec.png)

**例 2:** 在 spread()方法中增加半径值。

```
# Import Image from wand.image module
from wand.image import Image

# Read image using Image() function
with Image(filename ="koala.jpeg") as img:

    # Generate spread image using spread() function
    img.spread(radius = 16.0)
    img.save(filename ="spreadkoala2.jpg")
```

**输出:**
![](img/0cb1ebef54763d6d209936ee24ffacfe.png)
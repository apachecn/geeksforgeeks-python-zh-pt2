# 魔杖–转换图像格式

> 原文:[https://www.geeksforgeeks.org/wand-convert-image-format/](https://www.geeksforgeeks.org/wand-convert-image-format/)

**图像格式**描述图像数据是如何存储的。不同的图像格式有不同的优缺点。大约有 7 种最常见的图像格式用于不同的情况。
例如–JPEG 格式的优势在于它支持 24 位颜色，最高支持 1600 万种颜色。因此，具有高分辨率。而巴布亚新几内亚格式分辨率较低。

**图像文件格式:**T2]1。JPEG(.jpeg)
2 .PNG(.png)
3 .TIFF(.tif or.tiff)
4 .GIF(.gif)
5。位图(.bmp)
6 .EPS(.eps)

**注:**要详细学习图像格式，请参考–[图像格式篇](https://www.geeksforgeeks.org/image-formats/)。

我们可以使用 Python 中的魔杖库使用`format`属性将一种[图像格式](https://www.geeksforgeeks.org/image-formats/)转换为另一种。

**语法:**

```
wand.image.format = 'final_format'

```

**代码:**

```
# import Image from wand.image module
from wand.image import Image

# Read .png image using Image() function
with Image(filename ='koala.png') as img:

    # Change format in python using format property
    img.format = 'jpeg'

    # Save final image
    img.save(filename ='koala.jpg')
```

在输出中，我们将获得一个名为`koala.jpeg`的 jpeg 图像格式的图像。
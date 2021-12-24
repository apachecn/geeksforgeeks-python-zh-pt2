# Python–使用魔杖库

读取 Python 中的 blob 对象

> 原文:[https://www . geesforgeks . org/python-read-blob-object-in-python-use-wand-library/](https://www.geeksforgeeks.org/python-read-blob-object-in-python-using-wand-library/)

BLOB 代表二进制大对象。blob 是一种可以存储二进制数据的数据类型。这不同于数据库中使用的大多数其他数据类型，如整数、浮点数、字符和字符串，它们存储字母和数字。BLOB 是存储在数据库中的二进制数据的大型复杂集合。基本上，BLOB 用于存储媒体文件，如图像、视频和音频文件。由于它能够存储多媒体文件，因此需要巨大的磁盘空间。BLOB 的长度也可以达到 2，147，483，647 个字符。BLOB 提供快速的多媒体传输。
**从图像中获取斑点文件:**

```py
     with open('*image_path*') as f:
    image_blob = f.read()
```

**从魔杖中的斑点读取图像:**

```py
with Image(blob=image_binary) as img:
    \\other code
```

**输入图像:**

![](img/a1d5dabac07efe8de363e0c440a198d8.png)

**代码:**

## 蟒蛇 3

```py
# import required libraries
from __future__ import print_function

# import Image from wand.image module
from wand.image import Image

# open image using file handling
with open('koala.jpeg') as f:

    # get blob from image file
    image_blob = f.read()

# read image using wand from blob file
with Image(blob = image_binary) as img:

    # get height of image
    print('height =', img.height)

    # get width of image
    print('width =', img.width)
```

**输出:**

```py
height = 300
width = 400
```
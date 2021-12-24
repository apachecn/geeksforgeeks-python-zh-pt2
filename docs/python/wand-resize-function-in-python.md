# Python 中的魔杖调整大小()功能

> 原文:[https://www . geesforgeks . org/wand-resize-function-in-python/](https://www.geeksforgeeks.org/wand-resize-function-in-python/)

调整图像大小是指改变原始图像的尺寸，以便将原始图像转换为适合使用的尺寸。**缩小**是指缩小图像尺寸，使图像尺寸变小。而**放大**是指增加图像的尺寸，使图像尺寸变大。
使用 resize()函数来调整图像的大小。

> **语法:**
> 
> ```
> wand.image.resize(width=None, height=None, filter='undefined', blur=1)
> ```
> 
> **参数:**
> 
> <figure class="table">
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 宽度 | 数字。积分 | 图像的新宽度 |
> | 高度 | 数字。积分 | 图像的新高度 |
> | 过滤器 | 基本字符串或数字。积分 | 用于调整大小的筛选器类型。 |
> | 虚化 | 数字。真实的 | 大于 1 的模糊因子是模糊的，< 1 的模糊因子是清晰的 |
> 
> </figure>

**示例 1 :**
**输入图像:**

![](img/8f3c46cc3669b3946d753f96e4d79132.png)

## 蟒蛇 3

```
# import Image from wand.image
from wand.image import Image

# read image using Image() function
with Image(filename = 'gog.png') as img:
    # resize image using resize() function
    img.resize(50, 50, filter = 'undefined, blur = 1)

    # save resized image
    img.save(filename = 'resized_gog.png')
```

**输出:**

![](img/c184c6cf6876f170f593e9aebb7d8bae.png)

**示例 2 :**
***输入图像:***
*输入将来自一个 url。*[*geeks forgeeks*](https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png)

## *蟒蛇 3*

```
*# import required libraries
import urllib3
from cStringIO import StringIO
from wand.image import Image
from wand.display import display

# load image from url
http = urllib3.PoolManager()
r = http.request('GET', 'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png')
f = StringIO(r.data)

# read image using Image() function
with Image(file=f) as img:

    # resize image using resize() function
    img.resize(400, 300)

    # save image 
    img.save(filename = 'gogurl.png')

    # display final image
    display(img)*
```

****输出:****

*![](img/12d1d8b5a1e91654d6b177684d357e45.png)*
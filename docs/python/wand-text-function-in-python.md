# Python 中的魔杖文本()函数

> 原文:[https://www.geeksforgeeks.org/wand-text-function-in-python/](https://www.geeksforgeeks.org/wand-text-function-in-python/)

也可以使用 wand.drawing 对象添加文本。 **text()** 功能用于在 Drawing 对象中添加文本。它采用 x 和 y 坐标以及我们想要写在(x，y)位置上的字符串。

> **语法:**
> 
> ```
> wand.drawing.text(x, y, body)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | x | 数字。积分 | 开始书写文本的基线。 |
> | y | 数字。积分 | 开始书写文本的左侧偏移量。 |
> | 身体 | 基绳 | 要写入的正文字符串。 |

**示例#1:**

```
# Import different modules of wand
from wand.image import Image
from wand.drawing import Drawing
from wand.color import Color
import math

with Drawing() as draw:
    with Image(width = 200, height = 200, background = Color('lightgreen')) as image:

        draw.font = 'wandtests/assets/League_Gothic.otf'
        draw.font_size = 10
        draw.text(image.width / 2, image.height / 2, 'GeeksForGeeks')
        draw(image)
        image.save(filename = "text.png")
```

**输出:**
![](img/575bf9f3eccb8d72b8f4dcf63b1ed1e0.png)

**例 2:**

```
# Import different modules of wand
from wand.image import Image
from wand.drawing import Drawing
from wand.color import Color
import math

with Drawing() as draw:
    with Image(filename = "gog.png") as image:
        draw.font = 'wandtests / assets / League_Gothic.otf'
        draw.font_size = 10
        draw.text(image.width / 2, image.height / 2, 'GeeksForGeeks')
        draw(image)
        image.save(filename = "text.png")
```

**输出: **![](img/0b8ee8909c5964af8f68c81d2aedc2e9.png)****
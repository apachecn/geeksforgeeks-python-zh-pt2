# 魔杖内爆()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-implode-function-python/](https://www.geeksforgeeks.org/wand-implode-function-python/)

**内爆()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于通过将像素拉向图像中心来创建“内爆”效果。

> **语法:**
> 
> ```
> implode(amount, method)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **数量:**该参数存储 0.0 & 1.0 之间的归一化影响程度。
> *   **方法:**该参数存储插值方法。
> 
> **返回值:**该函数返回魔杖图像图像对象。

**原图:**

![](img/2d3a0fdbc25c0bbb46c47454d1b0acc7.png)

**例 1:**

## 蟒蛇 3

```
# Import library from Image
from wand.image import Image

# Import the image
with Image(filename ='../geeksforgeeks.png') as image:
    # Clone the image in order to process
    with image.clone() as implode:
        # Invoke implode function
        implode.implode(0.5, "blend")
        # Save the image
        implode.save(filename ='implode1.jpg')
```

**输出:**

![](img/38f88d6a3fd7f0797d0ab12248d094b1.png)

**例 2:**

## 蟒蛇 3

```
# Import libraries from the wand 
from wand.image import Image
from wand.drawing import Drawing
from wand.color import Color

with Drawing() as draw:
    # Set Stroke color the circle to black
    draw.stroke_color = Color('black')
    # Set Width of the circle to 2
    draw.stroke_width = 1
    # Set the fill color to 'White (# FFFFFF)'
    draw.fill_color = Color('white')

    # Invoke Circle function with center at 50, 50 and radius 25
    draw.circle((200, 200), # Center point
                (100, 100)) # Perimeter point
    # Set the font style
    draw.font = '../Helvetica.ttf'
    # Set the font size
    draw.font_size = 30

    with Image(width = 400, height = 400, background = Color('# 45ff33')) as pic:
        # Set the text and its location
        draw.text(int(pic.width / 3), int(pic.height / 2), 'GeeksForGeeks !')
        # Draw the picture
        draw(pic)
        # Invoke implode function
        pic.implode(0.7, "catrom")
        # Save the image
        pic.save(filename ='implode2.jpg')
```

**输出:**

![](img/e6d167389382c93a247ddec771d3301b.png)
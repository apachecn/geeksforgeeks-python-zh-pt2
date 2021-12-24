# 魔杖剃须()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-shave-function-python/](https://www.geeksforgeeks.org/wand-shave-function-python/)

**shave()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于从图像中移除像素。

> **语法:**
> 
> ```
> shave(columns, rows)
> ```
> 
> **参数:**该功能接受上述四个参数，定义如下:
> 
> *   **列:**此参数用于设置 x 轴两侧的刮除量。
> *   **行:**此参数用于设置 y 轴两侧的刮除量
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
    with image.clone() as shave:
        # Invoke shave function
        shave.shave(50, 50)
        # Save the image
        shave.save(filename ='shave1.jpg')
```

**输出:**

![](img/1b8ad4e5178169002441024adad378d5.png)

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
        # Invoke shave function method
        pic.shave(40, 45)
        # Save the image
        pic.save(filename ='shave2.jpg')
```

**输出:**

![](img/4cee1bd69b2d0cf6f31a9abfb60e4295.png)
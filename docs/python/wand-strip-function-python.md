# 魔杖条()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-strip-function-python/](https://www.geeksforgeeks.org/wand-strip-function-python/)

**剥离()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于剥离所有配置文件和注释的图像。

> **语法:**
> 
> ```py
> strip()
> ```
> 
> **参数:**该功能不接受任何参数。
> **返回值:**该函数返回魔杖图像魔法对象。

**原图:**

![](img/2d3a0fdbc25c0bbb46c47454d1b0acc7.png)

**例 1:**

## 蟒蛇 3

```py
# Import library from Image
from wand.image import Image

# Import the image
with Image(filename ='../geeksforgeeks.png') as image:
    # Clone the image in order to process
    with image.clone() as strip:
        # Invoke strip function
        strip.strip()
        # Save the image
        strip.save(filename ='strip1.jpg')
```

**输出:**

![](img/1ee1d81eb7b4f3ba6e47e2332ebae5a6.png)

**例 2:**

## 蟒蛇 3

```py
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
        # Invoke strip function
        pic.strip()
        # Save the image
        pic.save(filename ='strip2.jpg')
```

**输出:**

![](img/fc419021e985f237bf0db14600eff67b.png)
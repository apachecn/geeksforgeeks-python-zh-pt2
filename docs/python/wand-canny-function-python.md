# 魔杖 canny()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-canny-function-python/](https://www.geeksforgeeks.org/wand-canny-function-python/)

**canny()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于通过利用多阶段 canny 算法来检测边缘。

> **语法:**
> 
> ```py
> canny(radius, sigma, lower_percent, upper_percent)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **半径:**该参数存储高斯滤波器的半径。
> *   **σ:**此参数存储高斯滤波器的标准偏差。
> *   **下限百分比:**存储标准化下限阈值的参数。
> *   **上限百分比:**存储标准化上限阈值的参数。
> 
> **返回值:**该函数返回魔杖图像图像对象。

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
    with image.clone() as canny:
        # Invoke canny function
        canny.canny(3, 2, 0.2, 0.8)
        # Save the image
        canny.save(filename ='canny1.jpg')
```

**输出:**

![](img/4340f9cfba4e33cbaf1339ba7fc0f518.png)

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
        # Invoke canny function
        pic.canny(4, 2, 0.3, 0.7)
        # Save the image
        pic.save(filename ='canny2.jpg')
```

**输出:**

![](img/0f28fcb3b473a0fa51534aef237daa28.png)
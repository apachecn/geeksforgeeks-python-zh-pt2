# 魔杖晕影()方法–Python

> 原文:[https://www.geeksforgeeks.org/wand-vignette-method-python/](https://www.geeksforgeeks.org/wand-vignette-method-python/)

**晕影(()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于在图像上创建晕影样式的效果。与图像中心相比，它向外围降低了图像亮度或饱和度。

> **语法:**
> 
> ```py
> vignette(radius, sigma, x, y)
> ```
> 
> **参数:**该功能接受上述四个参数，定义如下:
> 
> *   **半径:**此参数存储高斯模糊效果的半径。
> *   **适马:**该参数存储高斯效应的标准差。
> *   **x:** 此参数存储从图像顶部&底部向内偏移的像素数。
> *   **y:** 该参数存储从图像左侧&向右侧向内偏移的像素数。
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
    with image.clone() as vignette:
        # Invoke vignette function with radius as 12, sigma as 10,
        # x as 20, y as 20
        vignette.vignette(12, 10, 20, 20)
        # Save the image
        vignette.save(filename ='vignette1.jpg')
```

**输出:**

![](img/bb6761599970f7b87763ef16395433e6.png)

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
        # Invoke vignette function with radius as 12, sigma as 10, x as 10
        # y as 10
        pic.vignette(12, 10, 10, 10)
        # Save the image
        pic.save(filename ='vignette2.jpg')
```

**输出:**

![](img/d56b445c6ba515affc15a4e5ac0be2b1.png)
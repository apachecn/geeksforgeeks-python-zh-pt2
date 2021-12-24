# 棒夹()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-clamp-function-python/](https://www.geeksforgeeks.org/wand-clamp-function-python/)

**clamp()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于将颜色值限制在 0 和量程范围之间。

> **语法:**
> 
> ```
> canny(channel)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **通道:**这是一个可选参数，存储颜色通道，如“绿色”、“红色”、“黄色”等。
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
    with image.clone() as clamp:
        # Invoke clamp function
        clamp.clamp("red")
        # Save the image
        clamp.save(filename ='clamp1.jpg')
```

**输出:**

![](img/1d2a36ab7ad4494c2169ffa280299ca5.png)

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
        # Invoke clamp function
        pic.clamp('green')
        # Save the image
        pic.save(filename ='clamp2.jpg')
```

**输出:**

![](img/ab356376b330f686a403aafdd6a032f7.png)
# 魔杖归一化()函数–Python

> 原文:[https://www . geesforgeks . org/wand-normalize-function-python/](https://www.geeksforgeeks.org/wand-normalize-function-python/)

**normalize()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于通过计算直方图来规范化图像的颜色。

> **语法:**
> 
> ```
> normalize(channel)
> ```
> 
> **参数:**该功能接受单参数作为通道类型。
> **返回值:**该函数返回魔杖图像魔法对象。

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
    with image.clone() as normalize:

        # Invoke normalize function with Channel "green"
        normalize.normalize("green")

        # Save the image
        normalize.save(filename ='normalize1.jpg')
```

**输出:**

![](img/f6ce47a7d4e9432f0f7fa93a515f2143.png)

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
        # Invoke normalize function with channel "yellow"
        pic.normalize("yellow")
        # Save the image
        pic.save(filename ='normalize2.jpg')
```

**输出:**

![](img/355d5f2c5ca965febcd21dfe1457490e.png)
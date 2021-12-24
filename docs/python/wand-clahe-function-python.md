# 魔杖 clahe()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-clahe-function-python/](https://www.geeksforgeeks.org/wand-clahe-function-python/)

**clahe()** 函数是 Python Wand ImageMagick 库中的内置函数，用于对比度受限的自适应直方图均衡化。

> **语法:**
> 
> ```
> clahe(width, height, number_bins, clip_limit)
> ```
> 
> **参数:**该功能接受上述四个参数，定义如下:
> 
> *   **宽度:**此参数存储区域的大小。
> *   **高度:**此参数存储区域的大小。
> *   **number _ bin:**此参数存储直方图的 bin。
> *   **clip_limit:** 此参数存储对比度限制。
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
    with image.clone() as clahe:
        # Invoke clahe function
        clahe.clahe(300, 200, 3.4, 2.7)
        # Save the image
        clahe.save(filename ='clahe1.jpg')
```

**输出:**

![](img/2d65f41684264648df0e42c6dc2cb238.png)

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
        # Invoke clahe function
        pic.clahe(300, 200, 3.4, 2.7)
        # Save the image
        pic.save(filename ='clahe2.jpg')
```

**输出:**

![](img/36596cd84a41743302faa3fafd9b3ea8.png)
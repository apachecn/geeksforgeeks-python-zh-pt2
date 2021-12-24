# 魔杖压花()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-emboss-function-python/](https://www.geeksforgeeks.org/wand-emboss-function-python/)

**浮雕()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于浮雕图像，这意味着图像的每个像素都被替换以产生 3D 效果。

> **语法:**
> 
> ```
> emboss(radius, sigma)
> ```
> 
> **参数:**该功能接受上述四个参数，定义如下:
> 
> *   **半径:**该参数存储木炭图像的半径。
> *   **σ:**该参数存储木炭图像的σ。
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
    with image.clone() as emboss:
        # Invoke emboss function
        emboss.emboss(0.1, 0.1)
        # Save the image
        emboss.save(filename ='emboss1.jpg')
```

**输出:**

![](img/9cf7070ca9fb97fd25f1226f4350c265.png)

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
        # Invoke emboss function
        pic.emboss(7, 3)
        # Save the image
        pic.save(filename ='emboss2.jpg')
```

**输出:**

![](img/2799146d51420968c20d822bcab7cde9.png)
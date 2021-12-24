# 魔杖乙状结肠 _ 对比()功能–Python

> 原文:[https://www . geeksforgeeks . org/wand-sigminal _ contrast-function-python/](https://www.geeksforgeeks.org/wand-sigmoidal_contrast-function-python/)

**sigmoxic _ contrast()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于模拟铅笔草图效果。

> **语法:**
> 
> ```py
> sigmoidal_contrast(sharpen, strength, midpoint, channel)
> ```
> 
> **参数:**该功能接受上述四个参数，定义如下:
> 
> *   **锐化:**这是一个布尔参数，表示是否需要锐化。
> *   **强度:**该参数存储对比度的强度。
> *   **中点:**该参数存储归一化值。
> *   **通道:**此参数存储可用于插值的通道。
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
    with image.clone() as sigmoidal_contrast:
        # Invoke sigmoidal_contrast function
        sigmoidal_contrast.sigmoidal_contrast(True, 10, 10)
        # Save the image
        sigmoidal_contrast.save(filename ='sigmoidal_contrast1.jpg')
```

**输出:**

![](img/2943bf004f824c9719483c95a5097d15.png)

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
        # Invoke sigmoidal_contrast function method
        pic.sigmoidal_contrast(False, 5, 18)
        # Save the image
        pic.save(filename ='sigmoidal_contrast2.jpg')
```

**输出:**

![](img/6794448083139820c2e594c1c2de267c.png)
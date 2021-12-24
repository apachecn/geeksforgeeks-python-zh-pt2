# 魔杖阴影()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-shadow-function-python/](https://www.geeksforgeeks.org/wand-shadow-function-python/)

**阴影()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于生成图像阴影。

> **语法:**
> 
> ```py
> shadow(alpha, sigma, x, y)
> ```
> 
> **参数:**该函数接受上面提到的四个参数，定义如下:
> 
> *   **α:**此参数存储透明度的比率。
> *   **sigma:** 该参数存储锐化图像的 sigma 级别。
> *   **x:** 此参数存储 x 偏移。
> *   **y:** 此参数存储 y 偏移。
> 
> **返回值:**该函数返回魔杖图像图像对象。

**原图:**
![](img/2d3a0fdbc25c0bbb46c47454d1b0acc7.png)
**例 1:**

```py
# Import library from Image 
from wand.image import Image

# Import the image
with Image(filename ='../geeksforgeeks.png') as image:
    # Clone the image in order to process
    with image.clone() as shadow:
        # Invoke shadow function
        shadow.shadow(0.8, 0.2, 10, 40)
        # Save the image
        shadow.save(filename ='shadow1.jpg')
```

**输出:**
![](img/05fcbe02c29f5585c049eb7a6174d383.png)

**例 2:**

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
        # Invoke shadow function method 
        pic.shadow(0.3, .1, 1, 2)
        # Save the image 
        pic.save(filename ='shadow2.jpg')
```

**输出:**
![](img/7255b26061e75b93f437ce0579d97be7.png)
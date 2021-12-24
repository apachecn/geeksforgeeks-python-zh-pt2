# 魔杖样本()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-sample-function-python/](https://www.geeksforgeeks.org/wand-sample-function-python/)

**sample()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于通过对像素进行采样来更改图像大小。它比 resize()更快，但提供的图像质量更低。

> **语法:**
> 
> ```py
> sample(width, height)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **宽度:**此参数存储样本图像的宽度。
> *   **高度:**该参数存储样本图像的高度。
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
    with image.clone() as sample:
        # Invoke sample function with threshold as 0.8
        sample.sample(200, 100)
        # Save the image
        sample.save(filename ='sample1.jpg')
```

**输出:**

![](img/6c46500b71ebb3b953405b9c82fbf372.png)

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
        # Invoke sample function method with threshold 0.6
        pic.sample(50, 100)
        # Save the image
        pic.save(filename ='sample2.jpg')
```

**输出:**

![](img/41a3eda5875c9ff3d806cd894bdad77c.png)
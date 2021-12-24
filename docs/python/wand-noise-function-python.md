# 魔杖噪音()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-noise-function-python/](https://www.geeksforgeeks.org/wand-noise-function-python/)

**噪波()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于为图像添加噪波。

> **语法:**
> 
> ```
> noise(noise_type, attenuate, channel)
> ```
> 
> **参数:**该函数接受三个参数，如上所述，定义如下:
> 
> *   **噪声 _ 类型:**此参数用于存储噪声类型。一些可用的噪声类型是‘未定义’‘均匀’‘高斯’‘乘法 _ 高斯’‘脉冲’‘拉普拉斯’‘泊松’‘随机’。
> *   **衰减:**该参数存储分布速率。
> *   **通道:**该参数将通道类型存储为“绿色”、“黄色”、“红色”等。
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
    with image.clone() as noise:
        # Invoke noise function with Channel "green" and noise poisson
        noise.noise("poisson", 2, "green")
        # Save the image
        noise.save(filename ='noise1.jpg')
```

**输出:**

![](img/6df3e95f34f6047f7db76eeee5f1e08b.png)

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
        # Invoke noise function with channel "yellow" and noise as impulse
        pic.noise("impulse", 3, "yellow")
        # Save the image
        pic.save(filename ='noise2.jpg')
```

**输出:**

![](img/77a921829e05f966708b9776b17e0eff.png)
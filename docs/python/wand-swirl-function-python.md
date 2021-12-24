# 魔杖漩涡()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-swirl-function-python/](https://www.geeksforgeeks.org/wand-swirl-function-python/)

**漩涡()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于围绕图像中心旋转。度数指定漩涡的紧密度。

> **语法:**
> 
> ```
> swirl(degree, method)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **度:**该参数存储 0 至 360°之间的角度。
> *   **方法:**该参数存储控制受影响像素插值的方法。一些可用的方法是“未定义”、“平均”、“平均 9”、“平均 16”、“背景”、“双线性”、“混合”、“catrom”、“整数”、“网格”、“最近”、“样条”
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
    with image.clone() as swirl:
        # Invoke swirl function with degree as 100 and method ss 'blend'
        swirl.swirl(100, 'blend')
        # Save the image
        swirl.save(filename ='swirl1.jpg')
```

**输出:**

![](img/9b523415823082eb304fc23f9d40a09e.png)

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
        # Invoke swirl function with degree as 150 and method as bilinear
        pic.swirl(150, 'bilinear')
        # Save the image
        pic.save(filename ='swirl2.jpg')
```

**输出:**

![](img/fbbafab80882f6754a4e0b551a4ca8ad.png)
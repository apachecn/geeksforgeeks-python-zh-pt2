# 棒剪()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-shear-function-python/](https://www.geeksforgeeks.org/wand-shear-function-python/)

**shear()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于沿着 X 轴或 Y 轴滑动图像的一条边以创建平行四边形。X 方向的剪切沿着 X 轴滑动一条边，而 Y 方向的剪切沿着 Y 轴滑动一条边。剪切角度用于设置图像的剪切。

> **语法:**
> 
> ```
> shear(background, x, y)
> ```
> 
> **参数:**该功能接受上述四个参数，定义如下:
> 
> *   **背景:**该参数存储背景颜色。
> *   **x:** 此参数用于设置图像的 x 剪切度。
> *   **y:** 此参数用于设置图像的 y 剪切度。
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
    with image.clone() as shear:
        # Invoke shear function
        shear.shear('Red', 20, 30)
        # Save the image
        shear.save(filename ='shear1.jpg')
```

**输出:**

![](img/80a3eb871239acc0287f4e7afedd3be1.png)

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
        # Invoke shear function method
        pic.shear('Green', 30, 45)
        # Save the image
        pic.save(filename ='shear2.jpg')
```

**输出:**

![](img/143dc2f74fd9ba520c33abc8dfa3c1f1.png)
# 魔杖反锐化掩模()功能–Python

> 原文:[https://www . geesforgeks . org/wand-unsharpp _ mask-function-python-2/](https://www.geeksforgeeks.org/wand-unsharp_mask-function-python-2/)

**反锐化掩模()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于锐化图像。该函数将图像与给定半径和标准偏差的高斯算子卷积。

> **语法:**
> 
> ```
> unsharp_mask(radius, sigma, amount, threshold, channel)
> ```
> 
> **参数:**该功能接受上述四个参数，定义如下:
> 
> *   **半径:**此参数存储高斯模糊效果的半径。
> *   **适马:**该参数存储高斯效应的标准差。
> *   **数量:**此参数存储原始图像和添加回原始图像的模糊图像之间的差异百分比。
> *   **阈值:**该参数以像素为单位存储应用差值所需的阈值。
> *   **通道:**此参数用于将图像通道的值指定为未定义、‘红色’、‘灰色’、‘青色’、‘绿色’、‘品红色’、‘蓝色’、‘黄色’、‘alpha’、‘不透明度’、‘黑色’、‘索引’、‘composite _ channels’、‘all _ channels’、‘sync _ channels’、‘default _ channels’。
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
    with image.clone() as unsharp_mask:
        # Invoke unsharp_mask function with radius as 12, sigma as 10,
        # amount as 0.5, threshold as 0.8 and channel as 'Green'
        unsharp_mask.unsharp_mask(12, 10, 0.5, 0.8, 'Green')
        # Save the image
        unsharp_mask.save(filename ='unsharp_mask1.jpg')
```

**输出:**

![](img/e5cd4e223462dfb9c1887f4565a004b0.png)

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
        # Invoke unsharp_mask function with radius as 10, sigma as 5,
        # amount as 0.8, threshold as 0.5 and channel as 'Red'
        pic.unsharp_mask(10, 5, 0.8, 0.5, 'Red')
        # Save the image
        pic.save(filename ='unsharp_mask2.jpg')
```

**输出:**

![](img/9fa0c7132b5c8cbd3c4d51ebc0703c5c.png)
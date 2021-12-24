# 魔杖统计功能–Python

> 原文:[https://www . geesforgeks . org/wand-statistics-function-python/](https://www.geeksforgeeks.org/wand-statistic-function-python/)

**统计()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于用相邻像素值的统计结果替换每个像素。宽度&高度定义了相邻像素的大小或孔径。

> **语法:**
> 
> ```
> statistic(stat, width, height, channel)
> ```
> 
> **参数:**该功能接受上述四个参数，定义如下:
> 
> *   **stat:** 此参数存储要计算的统计类型。一些可用的统计数据是“未定义”、“梯度”、“最大值”、“平均值”、“中值”、“最小值”、“模式”、“非峰值”、“均方根”、“标准差”。
> *   **宽度:**此参数存储 X 轴上相邻像素的大小。
> *   **高度:**此参数存储 Y 轴上相邻像素的大小。
> *   **通道:**该参数存储可用的颜色通道。
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
    with image.clone() as statistic:
        # Invoke statistic function with statistic as median, width as 20
        # height as 10, channel as 'yellow'
        statistic.statistic('median', 20, 10, 'yellow')
        # Save the image
        statistic.save(filename ='statistic1.jpg')
```

**输出:**

![](img/3d6a48e67e924d1508286f996a32769a.png)

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
        # Invoke statistic function with statistic as root_mean_square, width as 20
        # height as 10, channel as 'green'
        pic.statistic('root_mean_square', 20, 10, 'green')
        # Save the image
        pic.save(filename ='statistic2.jpg')
```

**输出:**

![](img/e82b282a8bdefdd2050ef23a35eae27d.png)
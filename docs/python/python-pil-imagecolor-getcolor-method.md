# Python PIL |ImageColor.getcolor（） 方法

> 原文:[https://www . geesforgeks . org/python-pil-imagecolor-getcolor-method/](https://www.geeksforgeeks.org/python-pil-imagecolor-getcolor-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。ImageColor 模块包含颜色表和从 CSS3 风格的颜色说明符到 RGB 元组的转换器。该模块由 PIL 使用。Image.Image.new()和 ImageDraw 模块等。
**imagecolor . getcolor()**与 getrgb()相同，但如果模式不是彩色或调色板图像，则将 rgb 值转换为灰度值。如果无法解析字符串，此函数将引发 ValueError 异常。

> **语法:** PIL。ImageColor.getcolor(颜色，模式)
> **参数:**
> **颜色**–一个颜色字符串
> **返回:**(灰度[，alpha])或(红，绿，蓝[，alpha])

## 蟒蛇 3

```
# importing Image module from PIL package
from PIL import Image, ImageColor

# using getcolor
im = ImageColor.getcolor("orange", "L")
print(im)

im1 = ImageColor.getcolor("red", "L")
print(im1)
```
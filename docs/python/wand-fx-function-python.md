# 魔杖 fx()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-fx-function-python/](https://www.geeksforgeeks.org/wand-fx-function-python/)

FX 特效是一种强大的“微型”语言。简单的函数和操作符提供了一种访问和操作图像数据的独特方式。fx()方法应用 FX 表达式，并生成一个新的图像实例。

我们可以创建一个自定义的 DIY 滤镜，将图像变成黑色和白色，除了色调高于 324 或低于 36 的颜色。

> **语法:**
> 
> ```py
> wand.image.fx(fx_string)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 表示 | 基绳 | 要应用的整个 FX 表达式。 |
> | 频道 | 频道 | 可选目标频道。 |

**来源影像:**
![](img/a1d5dabac07efe8de363e0c440a198d8.png)

**例 1:**

```py
# import IMage from wand.image module
from wand.image import Image

# expression string for fx()
fx_filter ="(hue > 0.9 || hue < 0.1) ? u : lightness"

with Image(filename ="koala.jpeg") as img:
    with img.fx(fx_filter) as filtered_img:
       filtered_img.save(filename ="fx-koala.jpeg")
```

**输出:**
![](img/96ac5d735d579dda7111bd3444466e9f.png)

**例 2:**

```py
# import IMage from wand.image module
from wand.image import Image

# expression string for fx()
fx_filter ="(luma > 0.9 || luma < 0.1) ? u : lightness"

with Image(filename ="koala.jpeg") as img:
    with img.fx(fx_filter) as filtered_img:
       filtered_img.save(filename ="fx-koala.jpeg")
```

**输出:**
![](img/6042b0d95252dc96a4f9293747325dd5.png)
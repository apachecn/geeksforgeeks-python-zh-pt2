# Python PIL | ImageMath.eval()方法

> 原文:[https://www . geesforgeks . org/python-pil-image math-eval-method/](https://www.geeksforgeeks.org/python-pil-imagemath-eval-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

**`ImageMath`** 模块可用于评估“图像表情”。该模块提供了一个单独的 eval 函数，该函数接受一个表达式字符串和一个或多个图像。

`**PIL.ImageMath.eval()**`评估给定环境中的表达。

在当前版本中，ImageMath 仅支持单层图像。要处理多波段图像，请使用 split()方法或 merge()函数。

> **语法:** PIL。ImageMath.eval(表达式，环境)
> 
> **参数**:
> 
> **表达式**–使用标准 Python 表达式语法的字符串。除了标准操作符，您还可以使用下面描述的功能。
> **环境**–将图像名称映射到图像实例的字典。您可以使用一个或多个关键字参数来代替字典，如上例所示。请注意，名称必须是有效的 Python 标识符。
> 
> **根据表达式，返回类型:**图像、整数值、浮点值或像素元组。

**图片 1 使用:**
![](img/259bd809c8b459a33e042fc45632ace0.png)

**图片 2 使用:**
![](img/ee1e3e82d42af5694c89c469a0f5a294.png)

```py

# Importing Image module from PIL package 
from PIL import Image, ImageMath

# creating a image object
im1 = Image.open(r"C:\Users\System-Pc\Desktop\ybear.jpg").convert('L') 
im2 = Image.open(r"C:\Users\System-Pc\Desktop\leave.jpg").convert('L')

# applying the eval method

out = ImageMath.eval("convert(min(a, b), 'L')", a = im1, b = im2)
out.save("result.jpg")
out.show()
```

**输出:**

![](img/6d6f3fac945929e6366c2e6094365a0c.png)

**另一个例子:**这里我们把内置的 min()改为 max()。

```py
# Importing Image module from PIL package 
from PIL import Image, ImageMath

# creating a image object
im1 = Image.open(r"C:\Users\System-Pc\Desktop\ybear.jpg").convert('L') 
im2 = Image.open(r"C:\Users\System-Pc\Desktop\leave.jpg").convert('L')

# applying the eval method

out = ImageMath.eval("convert(max(a, b), 'L')", a = im1, b = im2)
out.save("result.jpg")
out.show()
```

**输出:**
![](img/8432bdd8391a3fee56b2d6ecd7f18981.png)
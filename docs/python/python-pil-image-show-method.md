# Python PIL | Image.show()方法

> 原文:[https://www.geeksforgeeks.org/python-pil-image-show-method/](https://www.geeksforgeeks.org/python-pil-image-show-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。图像模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。
**Image.sHOW()** 显示此图像。此方法主要用于调试目的。
在 Unix 平台上，此方法将图像保存到临时的 PPM 文件中，并调用 xv 实用程序。在 Windows 上，它将图像保存到一个临时的 BMP 文件中，并使用标准的 BMP 显示实用程序来显示它(通常是 Paint)。

> **语法:** Image.show(title=None，command=None)
> **参数:**
> **title**–可选标题，尽可能用于图像窗口。
> **命令**–用于显示图像的命令
> **返回类型** =分配的路径图像将打开。

**使用的图像:**

![](img/b9d9345df71fc8e6c101def0e1afd214.png)

## 蟒蛇 3

```py
# importing Image class from PIL package
from PIL import Image

# creating a object
im = Image.open(r"C:\Users\System-Pc\Desktop\home.png")

im.show()
```

**输出:**

![](img/b9d9345df71fc8e6c101def0e1afd214.png)

**另一个例子:**用 show()使用打开图像。jpg 扩展名。

**使用的图像:**

![](img/265b098c7c228c1351ae135294268ffd.png)

## 蟒蛇 3

```py
# importing Image class from PIL package
from PIL import Image

# creating a object
im = Image.open(r"C:\Users\System-Pc\Desktop\tree.jpg")

im.show()
```

**输出:**

![](img/265b098c7c228c1351ae135294268ffd.png)
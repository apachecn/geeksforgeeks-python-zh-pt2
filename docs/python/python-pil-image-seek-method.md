# Python PIL | Image.seek()方法

> 原文:[https://www.geeksforgeeks.org/python-pil-image-seek-method/](https://www.geeksforgeeks.org/python-pil-image-seek-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

**`Image.seek()`** 在这个序列文件中寻找给定的帧。如果您在序列的末尾寻找，该方法会引发 EOFError 异常。当序列文件打开时，库自动寻找帧 0。

请注意，在当前版本的库中，大多数序列格式只允许您查找下一帧。

> **语法:** Image.seek(帧)
> 
> **参数:**
> **帧**–帧数，从 0 开始。
> 
> **提升:**EOFError–如果呼叫试图寻求超出序列的结尾。

**所用图像:**
![](img/73fbbd53060797fe910e84fbf18b1aad.png)

```

# importing image class from PIL package
from PIL import Image

# creating gif image object
img = Image.open(r"C:\Users\System-Pc\Desktop\time.gif")
img1 = img.tell()
print(img1)

# using seek() method
img2 = img.seek(img.tell() + 1)
img3 = img.tell()
print(img3)
img.show()
```

**输出:**

```
0
1

```

![](img/73fbbd53060797fe910e84fbf18b1aad.png)
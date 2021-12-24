# Python PIL | Image.open()方法

> 原文:[https://www.geeksforgeeks.org/python-pil-image-open-method/](https://www.geeksforgeeks.org/python-pil-image-open-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**PIL.Image.open()**`打开并识别给定的图像文件。

这是一个懒惰的操作；此函数识别文件，但文件保持打开状态，并且直到您尝试处理数据(或调用 load()方法)时，才从文件中读取实际图像数据。请参见新()。

> **语法:** PIL。Image.open(fp，mode='r ')
> 
> **参数**:
> 
> **FP**–文件名(字符串)，路径名。路径对象或文件对象。文件对象必须实现 read()、seek()和 tell()方法，并以二进制模式打开。
> **模式**–该模式。如果给定，这个参数必须是“r”。
> 
> **返回类型**:图像对象。
> **引发**:IOError–如果找不到文件，或者图像无法打开和识别。

**所用图像:**
![](img/4b8bfc2d655bf1e4ef3e5cdd9f7f35db.png)

```py

# Imports PIL module 
from PIL import Image

# open method used to open different extension image file
im = Image.open(r"C:\Users\System-Pc\Desktop\ybear.jpg") 

# This method will show image in any image viewer 
im.show() 
```

**输出:**。JPG 扩展图像打开。

![](img/51c1a752ce01eeabd639dad93c068774.png)

**另一个例子:**这里我们用了。PNG 扩展名文件。

**所用图像:**
![](img/08a214a1e5988cf4929b6a61d30200e8.png)

```py

# Imports PIL module 
from PIL import Image

# open method used to open different extension image file
im = Image.open(r"C:\Users\System-Pc\Desktop\lion.png") 

# This method will show image in any image viewer 
im.show() 
```

**输出:**。png extension image open-png 延伸影像开启。
![](img/995fea3a18ae902e2d30828977ac071f.png)
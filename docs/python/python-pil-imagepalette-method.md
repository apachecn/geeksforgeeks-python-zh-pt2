# Python PIL | ImagePalette()方法

> 原文:[https://www . geesforgeks . org/python-pil-image palette-method/](https://www.geeksforgeeks.org/python-pil-imagepalette-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`ImagePalette`模块包含一个同名的类来表示调色板映射图像的调色板。

这个模块从未被很好地记录下来。不过，自 2001 年以来，这种情况一直没有改变，因此，如果需要的话，阅读源代码并找出内部结构可能是安全的。ImagePalette 类有几个方法，但它们都是“实验性的”
调色板映射图像的`**ImagePalette.ImagePalette()**`调色板。

> 语法:GDP。image palette . image palette(mode = ' RGB '，palette=None，size=0)
> 
> **参数:**
> **模式**–调色板使用的模式。
> **调色板**–可选调色板。
> **尺寸**–可选调色板尺寸。如果给定，它不能等于或大于 256。默认为 0。
> 
> **返回::**图像调色板对象。

**所用图像:**
![](img/686ce0abe8be10b924d2c483da582a22.png)

```

# importing Image module from PIL package 
from PIL import Image, ImagePalette

# opening a  image 
im = Image.open(r"C:\Users\System-Pc\Desktop\python.png") 

# ImagePalette
im1 = ImagePalette.ImagePalette(mode ='RGB', palette = None, size = 0)
print(im1)
```

**输出:**

```
PIL.ImagePalette.ImagePalette object at 0x000001930723FC50

```

**另一个例子:**用拍摄另一个图像。JPG 分机。

**所用图像:**
![](img/b108171cee1e623dac7ec29c84c23a4a.png)

```

# importing Image module from PIL package 
from PIL import Image, ImagePalette

# opening a  image 
im = Image.open(r"C:\Users\System-Pc\Desktop\scene4.jpg") 

# ImagePalette
im1 = ImagePalette.ImagePalette(mode ='RGB', palette = None, size = 0)
print(im1)
```

**输出:**

```
PIL.ImagePalette.ImagePalette object at 0x000001B8808AFCC0

```
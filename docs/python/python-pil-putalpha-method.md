# 蟒蛇 PIL |壳核()法

> 原文:[https://www.geeksforgeeks.org/python-pil-putalpha-method/](https://www.geeksforgeeks.org/python-pil-putalpha-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**Image.putalpha()**`在此图像中添加或替换 alpha 层。如果图像没有阿尔法层，它将被转换为“洛杉矶”或“RGBA”。新图层必须是“1”或“1”。

> **语法:** Image.putalpha(alpha)
> 
> **参数:**
> **阿尔法**–新的阿尔法层。这可以是与该图像具有相同大小的“L”或“1”图像，或者是整数或其他颜色值。
> 
> **返回:**一个图像对象。

**所用图像:**
![](img/e4dc81422db86e45320915b0dbc10a96.png)

```

# importing Image class from PIL package 
from PIL import Image 

# creating a object 
im = Image.open(r"C:\Users\System-Pc\Desktop\lion.png")

# using putalpha method
im.putalpha(1)

# show image object
im.show()
```

**输出:**
![](img/bd52191490d13401e0c2c4e06f7a5a35.png)

**另一个例子:**使用了另一个图像。

**所用图像:**
![](img/cd40b895346588a39797fa5b2f016557.png)

```

# importing Image class from PIL package 
from PIL import Image 

# creating a object 
im = Image.open(r"C:\Users\System-Pc\Desktop\butter.png")

# using putalpha method
im.putalpha(1)

# show image object
im.show()
```

**输出:**
![](img/822730e111ce9ea172f5782d8cb4eafd.png)
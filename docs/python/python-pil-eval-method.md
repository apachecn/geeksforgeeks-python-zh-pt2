# Python PIL | eval()方法

> 原文:[https://www.geeksforgeeks.org/python-pil-eval-method/](https://www.geeksforgeeks.org/python-pil-eval-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。 **`Image`** 模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**PIL.Image.eval()**`对给定图像中的每个像素应用该函数(该函数应该有一个参数)。如果图像有多个波段，相同的功能将应用于每个波段。请注意，对于每个可能的像素值，该函数只计算一次，因此不能使用随机分量或其他生成器。

> 语法:GDP。Image.eval(image、*args)
> 
> **参数** :
> **图像**–输入图像。
> **函数**–一个函数对象，取一个整数参数。
> 
> **返回类型**:图像。

**所用图像:**
![](img/a30ec4aa6b19027c5a2c951189a1e900.png)

```py

# Importing Image module from PIL package 
from PIL import Image 

# creating a image object
im2 = Image.open(r"C:\Users\System-Pc\Desktop\lion.PNG")

# applying the eval method
im3 = Image.eval(im2, (lambda x: 254 - x * 15))

im3.show() 
```

**输出:**

![](img/2a944d57a06035606c55ddc4cc69b246.png)

**另一个例子:**这里我们更改另一个图像的参数值。

**使用的图像–**
![](img/a6a62f33e59e9d685fa14fbb27737765.png)

```py
# Importing Image module from PIL package 
from PIL import Image 

# creating a image object
im2 = Image.open(r"C:\Users\System-Pc\Desktop\eval2image.PNG")

# applying the eval method
im3 = Image.eval(im2, (lambda x: 240 - x * 12))

im3.show()
```

**输出:**
![](img/0c8bc1dabf53d4ece9c19797874915c5.png)
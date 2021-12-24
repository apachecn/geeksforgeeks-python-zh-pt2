# python pil | imagefont . load _ default()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-pil-imagefont-load _ default/

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。
**`ImageFont`**模块定义了一个同名的类。该类的实例存储位图字体，并与 **`PIL.ImageDraw.Draw.text()`** 方法一起使用。

PIL 使用自己的字体文件格式来存储位图字体。您可以使用:命令` pilfont `实用程序将 BDF 和 PCF 字体描述符(X 窗口字体格式)转换为这种格式。

从 1.1.4 版本开始，PIL 可以配置为支持 TrueType 和 OpenType 字体(以及 FreeType 库支持的其他字体格式)。对于早期版本，TrueType 支持仅作为 imToolkit 包的一部分提供

`**ImageFont.load_default()**`加载一个“吃得健康活得健康”的默认字体。

> **语法:** ImageFont.load_default()
> 
> **参数:**
> **文字**-写文字加载。
> 
> **返回:**一个字体对象。

```py

from PIL import Image, ImageFont, ImageDraw

text = "eat healthy live healthy"
font = ImageFont.load_default()
im = Image.new("L", font.getsize(text), 255)

# document 
dctx = ImageDraw.Draw(im)
dctx.text((0, 0), text, font = font)
del dctx
im = im.resize((im.width * 6, im.height * 8))

# img is saved as specified
im.save("geeks3.png")
```

**输出:**
![](img/a3c6cbf4ccf50e9850a0cd2d17e9c7c2.png)

**另一个例子:**这里改变文本，加载一个“总比没有好”的默认字体。

```py

from PIL import Image, ImageFont, ImageDraw

text = "better than nothing"
font = ImageFont.load_default()
im = Image.new("L", font.getsize(text), 255)

# document 
dctx = ImageDraw.Draw(im)
dctx.text((0, 0), text, font = font)
del dctx
im = im.resize((im.width * 6, im.height * 6))

# img is saved as specified
im.save("geeks2.png")
```

**输出:**
![](img/b55c732c2011f7aa2547b8bb4ae022e7.png)
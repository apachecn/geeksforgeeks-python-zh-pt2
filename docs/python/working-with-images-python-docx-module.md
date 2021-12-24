# 使用图像–Python。docx 模块

> 原文:[https://www . geesforgeks . org/work-with-images-python-docx-module/](https://www.geeksforgeeks.org/working-with-images-python-docx-module/)

**先决条件:** [docx](https://www.geeksforgeeks.org/python-working-with-docx-module/)

Word 文档包含包装在三个对象级别中的格式化文本。最低级别运行对象、中等级别段落对象和最高级别文档对象。因此，我们不能使用普通的文本编辑器来处理这些文档。但是，我们可以使用 python-docx 模块在 python 中操作这些 word 文档。

Python docx 模块允许用户通过操作现有文档或创建一个新的空文档并对其进行操作来操作文档。这是一个强大的工具，因为它可以帮助您在很大程度上操作文档。要在 word 文档中添加图像，我们使用 **add_picture()方法**。无论何时调用，此方法都用于在 Word 文档中添加图像。

> **语法:** doc.add_picture(image_path，宽度=无，高度=无)
> 
> **参数:**
> 
> *   **image_path:** 是包含要添加的图像的路径的字符串。
> *   **宽度:**设置文档中要添加的图像的宽度。
> *   **高度:**设置文档中要添加的图像的高度。

在上面给出的函数中，没有指定高度和宽度，那么图像以其原始大小出现。

### 装置

安装该模块的 Pip 命令是:

```
pip install python-docx
```

### 方法

*   导入模块
*   创建 docx 对象
*   在需要插入图像的地方声明 add_picture()方法，以及该图像的路径和尺寸(可选)。
*   保存文档。

**示例 1:** 在 word 文档中添加原生大小的图像。

## 蟒蛇 3

```
# Import docx NOT python-docx
import docx

# Create an instance of a word document
doc = docx.Document()

# Add a Title to the document
doc.add_heading('GeeksForGeeks', 0)

# Image in its native size
doc.add_heading('Image in Native Size:', 3)
doc.add_picture('logo.png')

# Now save the document to a location
doc.save('gfg.docx')
```

**输出:**

![](img/5b32866112ba887302425adf5cd2f1f1.png)

**gfg.docx**

**示例 2:** 在 word 文档中添加定义大小的图像。

## 蟒蛇 3

```
# Import docx NOT python-docx
import docx
from docx.shared import Inches

# Create an instance of a word document
doc = docx.Document()

# Add a Title to the document
doc.add_heading('GeeksForGeeks', 0)

# Image with defined size
doc.add_heading('Image with Defined Size:', 3)
doc.add_picture('logo.png', width=Inches(2), height=Inches(2))

# Now save the document to a location
doc.save('gfg.docx')
```

**输出:**

![](img/5744a63361506c3b7267b35c56bd98ca.png)

**gfg.docx**
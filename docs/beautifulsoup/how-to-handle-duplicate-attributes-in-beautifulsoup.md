# 如何处理美丽组中的重复属性？

> 原文:[https://www . geesforgeks . org/如何处理-重复属性-in-beauty ulsup/](https://www.geeksforgeeks.org/how-to-handle-duplicate-attributes-in-beautifulsoup/)

有时在获取信息时，您在处理从相同标签的重复属性接收的信息时是否面临任何问题？如果是，那么阅读文章，清除你所有的疑虑。

一旦创建了存储项目的列表，编写下面给出的代码。

**语法:**

> list = soup . find _ all(“# Widget Name”，{“id”:#您要编辑的 Widget 的 Id 名称”})

编写以下代码后，从输出中移除属性，并从列表中打印您想要的特定项目。

### 方法:

*   导入模块
*   现在，通过输入您当前工作所在的 Python 文件的名称来删除路径的最后一段。

**语法:**

> base = OS . path . dirname(OS . path . abpath(#您当前工作的 Python 文件的名称')

*   然后，打开要从中读取值的 HTML 文件。

**语法:**

> html=open(os.path.join(base，' #您希望从中读取值的 html 文件的名称'))

*   解析美丽组中的 HTML 文件。
*   此外，创建一个列表来存储相同标签和属性的所有项目值。
*   接下来，找到所有具有相同标签和属性的项目。

**语法:**

> list = soup . find _ all(“# Widget Name”，{“id”:#您要编辑的 Widget 的 Id 名称”})

*   稍后，从标签中移除所有属性。
*   最后，打印小部件标签的特定项目。

**正在使用的网页:**

## 超文本标记语言

```py
<!DOCTYPE html>
<html>
 <head>
   Geeks For Geeks
 </head>
 <body>
 <div>
     <p id="vinayak">King</p>

     <p id="vinayak">Prince</p>

     <p id="vinayak">Queen</p>

 </div>
 <p id="vinayak">Princess</p>

  </body>
</html>
```

**程序:**

## 计算机编程语言

```py
# Import the libraries beautifulsoup and os
from bs4 import BeautifulSoup as bs
import os

# Remove the last segment of the path
# Here replace the name of your python file with
# gfg4.py
base = os.path.dirname(os.path.abspath("gfg4.py"))

# Open the HTML in which you want to make 
# changes
html = open(os.path.join(base, 'gfg.html'))

# Parse HTML file in Beautiful Soup
soup = bs(html, 'html.parser')

# Create a list to store the items
list = [3]

# Finding all the elements inside div
# with paragraph having id: vinayak
list = soup.div.find_all("p", {"id": "vinayak"})

# Removing attributes from the output
for i in list:
    i.attrs = {}

# Printing the value Prince
print(list[1])

# Printing the value Queen
print(list[2])
```

**输出:**

> 王子
> 
> 女王
# 使用漂亮的 Python 将 XML 结构转换为数据帧

> 原文:[https://www . geesforgeks . org/convert-XML-structure-to-data frame-using-beautulsoup-python/](https://www.geeksforgeeks.org/convert-xml-structure-to-dataframe-using-beautifulsoup-python/)

在这里，我们将使用 Python 的漂亮的输出包将 XML 结构转换成数据帧。这是一个用于抓取网页的 python 库。要安装这个库，命令是

```py
pip install beautifulsoup4
```

我们将使用这个库从一个 XML 文件中提取数据，然后我们将提取的数据转换成数据帧。为了转换成数据帧，我们需要安装熊猫的库。

**熊猫库:**是一个 python 库，用于数据操作和分析。要安装此库，命令是

```py
pip install pandas
```

注意:如果它要求你安装一个解析器库，使用命令

```py
pip install et_xmlfile
```

**分步实施:**

**步骤 1:** 导入库。

## 蟒 3

```py
from bs4 import BeautifulSoup  
import pandas as pd
```

首先，我们需要导入将要在程序中使用的库。在这里，我们从 bs4 模块导入了 BeautifulSoup 库，还导入了 pandas 库，并将其别名创建为“pd”。

**步骤 2:** 读取 xml 文件。

## 蟒 3

```py
file = open("gfg.xml",'r')
contents = file.read()
```

这里，我们在读取模式“r”下使用 open(“filename”、“mode”)函数打开名为“gfg.xml”的 xml 文件，并将其存储在变量“file”中。然后我们使用 read()函数读取存储在文件中的实际内容。

**第三步:**

## 蟒 3

```py
soup = BeautifulSoup(contents,'xml')
```

在这里，我们将存储在“contents”变量中的要抓取的文件的数据提供给 BeautifulSoup 函数，并传递 XML 类型的文件。

**第四步:**搜索数据。

这里，我们正在提取数据。我们正在使用 find_all()函数，该函数返回在该函数中传递的标签中存在的提取数据。

## 蟒 3

```py
authors = soup.find_all('author')
titles = soup.find_all('title')
prices = soup.find_all('price')
pubdate = soup.find_all('publish_date')
genres = soup.find_all('genre')
des = soup.find_all('description')
```

示例:

```py
authors = soup.find_all('author')
```

我们将提取的数据存储到作者变量中。这个 find_all('author ')函数将提取 xml 文件中 author 标记内的所有数据。数据将以列表的形式存储，也就是说，作者是从该 xml 文件中的所有作者标签中提取的数据的列表。其他陈述也一样。

**第 5 步:**从 xml 中获取文本数据。

## 蟒 3

```py
data = []
for i in range(0,len(authors)):
   rows = [authors[i].get_text(),titles[i].get_text(),
           genres[i].get_text(),prices[i].get_text(),
           pubdate[i].get_text(),des[i].get_text()]
   data.append(rows)
```
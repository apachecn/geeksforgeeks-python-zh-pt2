# 读取 Python 中的 CSV 文件

> 原文:[https://www.geeksforgeeks.org/reading-csv-files-in-python/](https://www.geeksforgeeks.org/reading-csv-files-in-python/)

**CSV(逗号分隔值)**文件是一种纯文本文档形式，它使用特定格式来组织表格信息。CSV 文件格式是一个有界文本文档，使用逗号来区分值。文档中的每一行都是数据日志。每个日志由一个或多个字段组成，用逗号分隔。它是导入和导出电子表格和数据库最流行的文件格式。

## 正在读取 CSV 文件

有多种方法可以读取使用 CSV 模块或熊猫库的 CSV 文件。

*   **csv 模块:**csv 模块是 Python 中的模块之一，提供了以 CSV 文件格式读写表格信息的类。
*   **pandas Library:**pandas Library 是开源 Python 库之一，为 Python 编程提供高性能、便捷的数据结构和数据分析工具及技术。

**读取 Python 中的 CSV 文件格式:**
考虑下面名为“巨人”的 CSV 文件。CSV:

![](img/ce3dc73a396b706700d65c36242b2a00.png)

*   **USing csv.reader():** 首先在' r '模式下使用 open()方法打开 csv 文件(打开文件时指定读取模式)，返回文件对象，然后使用 CSV 模块的 reader()方法读取，返回遍历指定 CSV 文档中所有行的 reader 对象。
    **注意:**关键字“with”与 open()方法一起使用，因为它简化了异常处理并自动关闭 CSV 文件。

## 蟒蛇 3

```py
import csv

# opening the CSV file
with open('Giants.csv', mode ='r')as file:

  # reading the CSV file
  csvFile = csv.reader(file)

  # displaying the contents of the CSV file
  for lines in csvFile:
        print(lines)
```

**输出:**

```py
['Organization', 'CEO', 'Established']
['Alphabet', 'Sundar Pichai', '02-Oct-15']
['Microsoft', 'Satya Nadella', '04-Apr-75']
['Amazon', 'Jeff Bezos', '05-Jul-94']
```

在上面的程序中，reader()方法用于读取将数据映射到列表中的巨人. csv 文件。

*   **使用 csv。DictReader()类:**与前面的方法类似，首先使用 open()方法打开 csv 文件，然后使用 CSV 模块的 DictReader 类读取该文件，该类的工作方式类似于常规阅读器，但将 CSV 文件中的信息映射到字典中。文件的第一行由字典键组成。

## 蟒蛇 3

```py
import csv

# opening the CSV file
with open('Giants.csv', mode ='r') as file:   

       # reading the CSV file
       csvFile = csv.DictReader(file)

       # displaying the contents of the CSV file
       for lines in csvFile:
            print(lines)
```

**输出:**

> ordereddct([(' Organization '，' Alphabet ')，(' CEO '，'桑德尔·皮帅')，(' Established '，' 02-10 月 15 日'))))
> ordereddct([(' Organization '，' Microsoft ')，(' CEO '，'塞特亚·纳德拉'，(' Established '，' 04-04-04-75 ')))))))
> ordereddct([(' Organization '，' Amazon '，(' CEO '，'杰夫·贝索斯')，(' Established '，' 05-

*   [**使用 pandas.read_csv()方法:**](https://www.geeksforgeeks.org/python-read-csv-using-pandas-read_csv/) 使用 pandas 库函数读取 csv 文件非常简单易行。这里熊猫库的 read_csv()方法用于从 csv 文件中读取数据。

## 蟒蛇 3

```py
import pandas

# reading the CSV file
csvFile = pandas.read_csv('Giants.csv')

# displaying the contents of the CSV file
print(csvFile)
```

**输出:**

```py
Organization            CEO Established
0   Alphabet  Sundar Pichai   02-Oct-15
1   Microsoft  Satya Nadella   04-Apr-75
2   Amazon     Jeff Bezos   05-Jul-94
```

在上面的程序中，熊猫库的 csv_read()方法读取巨人. csv 文件，并将其数据映射到 2D 列表中。
**注:**想了解更多关于熊猫的信息. csv_read() [点击这里](https://www.geeksforgeeks.org/python-read-csv-using-pandas-read_csv/)。
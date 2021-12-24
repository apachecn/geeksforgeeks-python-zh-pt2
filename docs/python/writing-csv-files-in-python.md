# 用 Python 写 CSV 文件

> 原文:[https://www.geeksforgeeks.org/writing-csv-files-in-python/](https://www.geeksforgeeks.org/writing-csv-files-in-python/)

**CSV(逗号分隔值)**是一种简单的文件格式，用于存储表格数据，如电子表格或数据库。CSV 文件以纯文本形式存储表格数据(数字和文本)。文件的每一行都是数据记录。每条记录由一个或多个字段组成，用逗号分隔。使用逗号作为字段分隔符是这种文件格式的名称来源。

Python 提供了一个名为`csv`的内置模块来处理 CSV 文件。本模块提供了各种用于写入 CSV 的类:

*   使用 csv.writer 类
*   使用 csv。DictWriter 类

## 使用 csv.writer 类

`csv.writer`类用于向 CSV 文件插入数据。此类返回一个 writer 对象，该对象负责将用户数据转换为分隔字符串。应该用`newline=''`打开 csvfile 对象，否则引用字段中的换行符将无法正确解释。

> **语法:** csv.writer(csvfile，方言='excel '，**fmtparams)
> 
> **参数:**
> **csvfile:** 一个带 write()方法的文件对象。
> **方言(可选):**要使用的方言名称。
> **fmtparams(可选):**格式化参数将覆盖方言中指定的参数。

`csv.writer`类提供了两种写入 CSV 的方法。他们是`writerow()`和`writerows()`。

*   **writerow():** This method writes a single row at a time. Field row can be written using this method.

    **语法:**

    ```py
    writerow(fields)

    ```

*   **writerows():** This method is used to write multiple rows at a time. This can be used to write rows list.

    **语法:**

    ```py
    Writing CSV files in Python
    writerows(rows)

    ```

**示例:**

```py
# Python program to demonstrate
# writing to CSV

import csv 

# field names 
fields = ['Name', 'Branch', 'Year', 'CGPA'] 

# data rows of csv file 
rows = [ ['Nikhil', 'COE', '2', '9.0'], 
         ['Sanchit', 'COE', '2', '9.1'], 
         ['Aditya', 'IT', '2', '9.3'], 
         ['Sagar', 'SE', '1', '9.5'], 
         ['Prateek', 'MCE', '3', '7.8'], 
         ['Sahil', 'EP', '2', '9.1']] 

# name of csv file 
filename = "university_records.csv"

# writing to csv file 
with open(filename, 'w') as csvfile: 
    # creating a csv writer object 
    csvwriter = csv.writer(csvfile) 

    # writing the fields 
    csvwriter.writerow(fields) 

    # writing the data rows 
    csvwriter.writerows(rows)
```

**输出:**

![python-write-to-csv](img/c9a01ba26bd3365fe11cbb9386a6c746.png)

## 使用 csv。DictWriter 类

这个类返回一个 writer 对象，它将字典映射到输出行。

> **语法:** csv。DictWriter(csvfile，fieldnames，restval= "，extrasaction = ' raise '，方言='excel '，*args，**kwds)
> 
> **参数:**
> **csvfile:** 一个带 write()方法的文件对象。
> **字段名:**标识字典中值传递顺序的键序列。
> **restval(可选):**指定在字段名中缺少关键字时要写入的值。
> **extraction(可选):**如果在字段名中找不到键，可选的 extraction 参数指示要采取的操作。如果设置为引发值，将引发错误。
> **方言(可选):**要使用的方言名称。

csv。DictWriter 提供了两种写入 CSV 的方法。它们是:

*   **writeheader():** `writeheader()` method simply writes the first row of your csv file using the pre-specified fieldnames.

    **语法:**

    ```py
    writeheader()

    ```

*   `writerows():` `writerows` method simply writes all the rows but in each row, it writes only the values(not keys).

    **语法:**

    ```py
    writerows(mydict)

    ```

**示例:**

```py
# importing the csv module 
import csv 

# my data rows as dictionary objects 
mydict =[{'branch': 'COE', 'cgpa': '9.0', 'name': 'Nikhil', 'year': '2'}, 
         {'branch': 'COE', 'cgpa': '9.1', 'name': 'Sanchit', 'year': '2'}, 
         {'branch': 'IT', 'cgpa': '9.3', 'name': 'Aditya', 'year': '2'}, 
         {'branch': 'SE', 'cgpa': '9.5', 'name': 'Sagar', 'year': '1'}, 
         {'branch': 'MCE', 'cgpa': '7.8', 'name': 'Prateek', 'year': '3'}, 
         {'branch': 'EP', 'cgpa': '9.1', 'name': 'Sahil', 'year': '2'}] 

# field names 
fields = ['name', 'branch', 'year', 'cgpa'] 

# name of csv file 
filename = "university_records.csv"

# writing to csv file 
with open(filename, 'w') as csvfile: 
    # creating a csv dict writer object 
    writer = csv.DictWriter(csvfile, fieldnames = fields) 

    # writing headers (field names) 
    writer.writeheader() 

    # writing data rows 
    writer.writerows(mydict) 
```

**输出:**

![python-csv](img/654e60fb7667ab9f9581cbc7322ba866.png)
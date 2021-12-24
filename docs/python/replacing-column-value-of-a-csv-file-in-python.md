# 在 Python 中替换 CSV 文件的列值

> 原文:[https://www . geesforgeks . org/replacing-column-value-of-a-CSV-file-in-python/](https://www.geeksforgeeks.org/replacing-column-value-of-a-csv-file-in-python/)

让我们看看如何在 Python 中替换 CSV 文件的列值。CSV 文件只是一个逗号分隔的文件。

**方法一:使用原生 Python 方式**

使用 **replace()** 方法，我们可以轻松地将一个文本替换为另一个文本。在下面的代码中，让我们输入一个 CSV 文件作为“csvfile.csv”，并以“读取”模式打开。join()方法将 CSV 文件的所有行放在一个 iterable 中，并将它们连接成一个字符串。然后，我们可以对整个字符串使用 replace()方法，并可以执行单次/多次替换。在整个字符串中，给定的文本被搜索并替换为指定的文本。

**示例:**

输入文件将是:

[![](img/0e2658b6efece0e367b4dd5bffd99508.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200826120157/csvfile.png)

## 蟒蛇 3

```py
# reading the CSV file
text = open("csvfile.csv", "r")

#join() method combines all contents of 
# csvfile.csv and formed as a string
text = ''.join([i for i in text]) 

# search and replace the contents
text = text.replace("EmployeeName", "EmpName") 
text = text.replace("EmployeeNumber", "EmpNumber") 
text = text.replace("EmployeeDepartment", "EmpDepartment") 
text = text.replace("lined", "linked") 

# output.csv is the output file opened in write mode
x = open("output.csv","w")

# all the replaced text is written in the output.csv file
x.writelines(text)
x.close()
```

**输出:**

[![](img/548c49463a9104835a54b6f298d72f14.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200826121205/output.png)

**方法二:使用熊猫数据框**

我们可以将 CSV 文件作为数据帧读取，然后应用 **replace()** 方法。

[![](img/db0902382a4cdf32e41a550506ac691a.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200826144538/csvfile1.png)

## 蟒蛇 3

```py
# importing the module
import pandas as pd 

# making data frame from the csv file 
dataframe = pd.read_csv("csvfile1.csv") 

# using the replace() method
dataframe.replace(to_replace ="Fashion", 
                 value = "Fashion industry", 
                  inplace = True)
dataframe.replace(to_replace ="Food", 
                 value = "Food Industry", 
                  inplace = True)
dataframe.replace(to_replace ="IT", 
                 value = "IT Industry", 
                  inplace = True)

# writing  the dataframe to another csv file
dataframe.to_csv('outputfile.csv', 
                 index = False)
```

**输出:**

[![](img/51f2a9a8cac7fae6972ec3cc2a678bbd.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200826150149/output1.png)
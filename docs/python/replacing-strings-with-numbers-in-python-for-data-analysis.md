# 在 Python 中用数字替换字符串进行数据分析

> 原文:[https://www . geesforgeks . org/用数据分析 python 中的数字替换字符串/](https://www.geeksforgeeks.org/replacing-strings-with-numbers-in-python-for-data-analysis/)

有时我们需要将熊猫数据帧中的字符串值转换成唯一的整数，这样算法才能表现得更好。因此，我们在熊猫数据帧中为字符串值分配唯一的数值。

**注意:执行前创建一个包含一些姓名和性别的. csv 文件**

假设我们有一个包含姓名和性别列的表格。在性别栏中，有两个类别男性和女性，假设我们要将 1 分配给男性，将 2 分配给女性。

示例:

```py
Input : 
---------------------
    |  Name  |  Gender
---------------------
 0    Ram        Male
 1    Seeta      Female
 2    Kartik     Male
 3    Niti       Female
 4    Naitik     Male 

Output :
    |  Name  |  Gender
---------------------
 0    Ram        1
 1    Seeta      2
 2    Kartik     1
 3    Niti       2
 4    Naitik     1 

```

**方法 1:**

```py
To create a dictionary containing two 
elements with following key-value pair:
Key       Value
male      1
female    2

```

然后使用 for 循环迭代数据框的性别列，并在找到键的地方替换这些值。

```py
# import pandas library
import pandas as pd

# creating file handler for 
# our example.csv file in
# read mode
file_handler = open("example.csv", "r")

# creating a Pandas DataFrame
# using read_csv function 
# that reads from a csv file.
data = pd.read_csv(file_handler, sep = ",")

# closing the file handler
file_handler.close()

# creating a dict file 
gender = {'male': 1,'female': 2}

# traversing through dataframe
# Gender column and writing
# values where key matches
data.Gender = [gender[item] for item in data.Gender]
print(data)
```

输出:

```py
    |  Name  |  Gender
---------------------
 0    Ram        1
 1    Seeta      2
 2    Kartik     1
 3    Niti       2
 4    Naitik     1 

```

**方法 2:**
方法 2 也类似，但不需要字典文件，代码行更少。在这种情况下，我们在内部迭代 DataFrame 的性别列，如果条件匹配，则更改值。

```py
# import pandas library
import pandas as pd

# creating file handler for
# our example.csv file in
# read mode
file_handler = open("example.csv", "r")

# creating a Pandas DataFrame
# using read_csv function that
# reads from a csv file.
data = pd.read_csv(file_handler, sep = ",")

# closing the file handler
file_handler.close()

# traversing through Gender 
# column of dataFrame and 
# writing values where
# condition matches.
data.Gender[data.Gender == 'male'] = 1
data.Gender[data.Gender == 'female'] = 2
print(data)
```

输出:

```py
    |  Name  |  Gender
---------------------
 0    Ram        1
 1    Seeta      2
 2    Kartik     1
 3    Niti       2
 4    Naitik     1 

```

****应用程序****

1.  这项技术可以应用于数据科学。假设我们正在处理一个包含“男性”和“女性”性别的数据集，那么我们可以分别分配“0”和“1”这样的数字，这样我们的算法就可以对数据进行处理。
2.  这种技术也可以应用于用新值替换数据集中的某些特定值。

****参考文献****

*   https://pandas . pydata . org
*   [https://pandas.pydata.org/pandas-docs/stable/tutorials.html](https://pandas.pydata.org/pandas-docs/stable/tutorials.html)
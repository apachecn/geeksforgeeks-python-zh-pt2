# Python 程序将列表 Dict 转换为 CSV

> 原文:[https://www . geesforgeks . org/python-program-to-convert-dict-of-list-to-CSV/](https://www.geeksforgeeks.org/python-program-to-convert-dict-of-list-to-csv/)

给定一个 d 列表的字典，任务是编写一个 Python 程序，将字典写入 CSV 文件。

解决这个问题的思路是先把字典压缩，然后写入 CSV 文件。Python 提供了一个名为“csv”的内置模块，用于处理 CSV 文件。csv.writer 类用于写入 csv 文件。csv.writer 类提供了两种写入 csv 文件的方法。

*   **writerow ():** T0】 writerow(): writerow is used to write a single line.
*   **writerows ():** T0】 writerows(): writerows is used to write multiple lines.

## 蟒 3

```py
# Program to write a dictionary of list to csv
import csv

# dictionary of list
d = {"key1": ['a', 'b', 'c'], 
     "key2": ['d', 'e', 'f'], 
     "key3": ['g', 'h', 'i']}

# writing to csv file
with open("test.csv", "w") as outfile:

    # creating a csv writer object
    writerfile = csv.writer(outfile)

    # writing dictionary keys as headings of csv
    writerfile.writerow(d.keys())

    # writing list of dictionary
    writerfile.writerows(zip(*d.values()))
```
# 在 Python 中将多个 CSV 文件读入单独的数据帧

> 原文:[https://www . geesforgeks . org/read-multi-CSV-files-in-separate-data frames-in-python/](https://www.geeksforgeeks.org/read-multiple-csv-files-into-separate-dataframes-in-python/)

在本文中，我们将看到如何将多个 CSV 文件读入单独的数据帧。对于只读取一个数据帧，我们可以使用熊猫的 [pd.read_csv()](https://www.geeksforgeeks.org/python-read-csv-using-pandas-read_csv/) 功能。它以一条路径作为输入，返回类似

```
df = pd.read_csv("file path")
```

的数据帧

我们来看看它是如何工作的

## 蟒 3

T5

```
# import module
import pandas as pd

# read dataset
df = pd.read_csv("./csv/crime.csv")
```
# 按升序或降序对 PySpark 数据框列进行排序

> 原文:[https://www . geesforgeks . org/sort-the-py spark-data frame-columns-按升序或降序排列/](https://www.geeksforgeeks.org/sort-the-pyspark-dataframe-columns-by-ascending-or-descending-order/)

在本文中，我们将对 pyspark 中的 dataframe 列进行排序。为此，我们使用 **sort()** 和 **orderBy()** 函数进行升序和降序排序。

让我们创建一个示例数据帧。

## 蟒 3

```
# importing module
import pyspark

# importing sparksession from 
# pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of employee data
data = [["1", "sravan", "company 1"],
        ["2", "ojaswi", "company 1"],
        ["3", "rohith", "company 2"],
        ["4", "sridevi", "company 1"],
        ["1", "sravan", "company 1"],
        ["4", "sridevi", "company 1"]]

# specify column names
columns = ['Employee_ID', 'Employee NAME', 'Company']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data, columns)

# display data in the dataframe
dataframe.show()
```
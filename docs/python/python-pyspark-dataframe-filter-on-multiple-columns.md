# Python PySpark–多列数据框过滤器

> 原文:[https://www . geesforgeks . org/python-py spark-data frame-多列过滤器/](https://www.geeksforgeeks.org/python-pyspark-dataframe-filter-on-multiple-columns/)

在本文中，我们将使用 Python 中 Pyspark 的 filter()和 where()函数来过滤多列上的数据帧。

**创建数据框以进行演示:**

## python 3

```py
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of employee data
data = [[1, "sravan", "company 1"],
        [2, "ojaswi", "company 1"], 
        [3, "rohith", "company 2"],
        [4, "sridevi", "company 1"],
        [1, "sravan", "company 1"],
        [4, "sridevi", "company 1"]]

# specify column names
columns = ['ID', 'NAME', 'Company']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data, columns)

# display dataframe
dataframe.show()
```
# 在 PySpark 中选择满足条件的列

> 原文:[https://www . geesforgeks . org/select-columns-in-a-condition-in-py spark/](https://www.geeksforgeeks.org/select-columns-that-satisfy-a-condition-in-pyspark/)

在本文中，我们将使用 Pyspark 中的 **where()** 函数根据条件选择数据框中的列。

让我们用员工数据创建一个示例数据框架。

## 蟒 3

```
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of employee data
data = [[1, "sravan", "company 1"], [2, "ojaswi", "company 1"],
        [3, "rohith", "company 2"], [4, "sridevi", "company 1"], 
        [1, "sravan", "company 1"], [4, "sridevi", "company 1"]]

# specify column names
columns = ['ID', 'NAME', 'Company']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data, columns)

# display dataframe
dataframe.show()
```
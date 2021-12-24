# 在 PySpark 数据框中显示不同的列值

> 原文:[https://www . geesforgeks . org/show-distinct-column-values-in-py spark-data frame/](https://www.geeksforgeeks.org/show-distinct-column-values-in-pyspark-dataframe/)

在本文中，我们将使用 Python 中的 pyspark 显示 dataframe 中不同的列值。为此，我们使用了 distinct()和 dropDuplicates()函数以及 select()函数。

让我们创建一个示例数据帧。

## 蟒 3

```py
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of employee data with 5 row values
data =[["1", "sravan", "company 1"],
       ["3", "bobby", "company 3"],
       ["2", "ojaswi", "company 2"],
       ["1", "sravan", "company 1"],
       ["3", "bobby", "company 3"],
       ["4", "rohith", "company 2"],
       ["5", "gnanesh", "company 1"]]

# specify column names
columns = ['Employee ID','Employee NAME','Company Name']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data,columns)

dataframe.show()
```
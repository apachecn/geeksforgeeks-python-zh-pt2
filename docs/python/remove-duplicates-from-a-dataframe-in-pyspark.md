# 从 PySpark

中的数据框中删除重复项

> 原文:[https://www . geesforgeks . org/remove-duplicates-from-a-data frame-in-py spark/](https://www.geeksforgeeks.org/remove-duplicates-from-a-dataframe-in-pyspark/)

在本文中，我们将使用 Python 中的 pyspark 从 dataframe 中删除重复的数据

在开始之前，我们将创建数据框进行演示:

## python 3

```
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of employee data
data =[["1","sravan","company 1"],
       ["2","ojaswi","company 1"],
       ["3","rohith","company 2"],
       ["4","sridevi","company 1"],
       ["1","sravan","company 1"],
       ["4","sridevi","company 1"]]

# specify column names
columns = ['Employee ID','Employee NAME','Company']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data,columns)

print('Actual data in dataframe')
dataframe.show()
```
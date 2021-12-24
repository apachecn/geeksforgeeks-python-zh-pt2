# 仅从 PySpark 数据框中选择数字或字符串列名

> 原文:[https://www . geesforgeks . org/select-only-numeric-or-string-columns-name-from-py spark-data frame/](https://www.geeksforgeeks.org/selecting-only-numeric-or-string-columns-names-from-pyspark-dataframe/)

在本文中，我们将讨论如何从 Spark DataFrame 中仅选择数字或字符串列名。

### **使用的方法:**

*   **创建数据帧:**此方法用于创建火花数据帧。
*   **isinstance:** 这是一个 Python 函数，用于检查指定的对象是否属于指定的类型。
*   **dtypes:** 它返回一个元组列表(columnNane，type)。返回的列表包含数据框中的所有列及其数据类型。
*   **schema.fields:** 用于访问 DataFrame 字段元数据。

**方法#1:**

在这个方法中，dtypes 函数用于获取元组列表(columnNane，type)。

## 蟒蛇 3

```py
from pyspark.sql import Row
from datetime import date
from pyspark.sql import SparkSession

spark = SparkSession.builder.getOrCreate()

# Creating dataframe from list of Row
df = spark.createDataFrame([
    Row(a=1, b='string1', c=date(2021, 1, 1)),
    Row(a=2, b='string2', c=date(2021, 2, 1)),
    Row(a=4, b='string3', c=date(2021, 3, 1))
])

# Printing DataFrame structure
print("DataFrame structure:", df)

# Getting list of columns and printing
# result
dt = df.dtypes
print("dtypes result:", dt)

# Getting list of columns having type
# string or bigint
# This statement will loop over all the 
# tuples present in dt list
# item[0] will contain column name and
# item[1] will contain column type
columnList = [item[0] for item in dt if item[1].startswith(
    'string') or item[1].startswith('bigint')]
print("Result: ", columnList)
```

**输出:**

```py
DataFrame structure: DataFrame[a: bigint, b: string, c: date]
dtypes result: [('a', 'bigint'), ('b', 'string'), ('c', 'date')]
Result:  ['a', 'b']
```

**方法 2:**

在此方法中**模式。**字段用于获取字段元数据，然后从元数据中提取列数据类型，并与所需的数据类型进行比较。

## 蟒蛇 3

```py
from pyspark.sql.types import StringType, LongType
from pyspark.sql import Row
from datetime import date
from pyspark.sql import SparkSession

# Initializing spark session
spark = SparkSession.builder.getOrCreate()

# Creating dataframe from list of Row
df = spark.createDataFrame([
    Row(a=1, b='string1', c=date(2021, 1, 1)),
    Row(a=2, b='string2', c=date(2021, 2, 1)),
    Row(a=4, b='string3', c=date(2021, 3, 1))
])

# Printing DataFrame structure
print("DataFrame structure:", df)

# Getting and printing metadata
meta = df.schema.fields
print("Metadata: ", meta)

# Getting list of columns having type 
# string or int
# This statement will loop over all the fields
# field.name will return column name and
# field.dataType will return column type
columnList = [field.name for field in df.schema.fields if isinstance(
    field.dataType, StringType) or isinstance(field.dataType, LongType)]
print("Result: ", columnList)
```

**输出:**

> data frame structure:data frame[a:bigint，b: string，c: date]
> 
> 元数据:[结构字段(a，LongType，true)，结构字段(b，StringType，true)，结构字段(c，DateType，true)]
> 
> 结果:['a '，' b']
# Python MongoDB –$ group(聚合)

> 原文:[https://www . geesforgeks . org/python-MongoDB-group-aggregation/](https://www.geeksforgeeks.org/python-mongodb-group-aggregation/)

[MongoDB](https://www.geeksforgeeks.org/mongodb-an-introduction/) 是一个开源的面向文档的数据库。MongoDB 以键值对的形式存储数据，是一个 NoSQL 数据库程序。NoSQL 这个术语的意思是非关系的。在本文中，我们将看到使用 Python 在 MongoDB 中使用 **$group** 。

## $组操作

在 PyMongo 中，**聚合方法**主要用于处理来自多个文档的数据记录，并将结果返回给用户。这是基于数据处理管道的，包括多个阶段，在这些阶段结束时，我们会得到汇总结果。聚合方法的一个阶段包括 **$group** 。此操作按照用户输入的指定标识符表达式对集合中的输入文档进行分组，然后将累加器表达式应用于它。然后它生成输出文档。

**$group** 包括以下内容-

1.  **_id-** 根据给定的 id 表达式对文档进行分组。
2.  **字段(可选)–**它包括应用于所包含文档的累加器表达式。

让我们通过一些例子来理解这一点。

**例 1:**

## 蟒 3

```py
from pymongo import MongoClient 

# creation of MongoClient 
client=MongoClient() 

# Connect with the portnumber and host 
client = MongoClient("mongodb://localhost:27017/") 

# Access database 
mydatabase = client['database'] 

# Access collection of the database 
mycollection=mydatabase['myTable'] 
writer_profiles = [
    {"_id":1, "user":"Amit", "title":"Python", "comments":5},
    {"_id":2, "user":"Drew",  "title":"JavaScript", "comments":15},
    {"_id":3, "user":"Amit",  "title":"C++", "comments":6},
    {"_id":4, "user":"Drew",  "title":"MongoDB", "comments":2},
    {"_id":5, "user":"Cody",  "title":"Perl", "comments":9}]

mycollection.insert_many(writer_profiles)
agg_result= mycollection.aggregate(
    [{
    "$group" : 
        {"_id" : "$user", 
         "num_tutorial" : {"$sum" : 1}
         }}
    ])
for i in agg_result:
    print(i)
```

**输出:**

```py
{'_id': 'Cody', 'num_tutorial': 1}
{'_id': 'Drew', 'num_tutorial': 2}
{'_id': 'Amit', 'num_tutorial': 2}

```

在上例中，文档是根据表达式 **$user** 、分组的，然后字段 **num_tutorial** 包含累加器运算符 **$sum** ，计算每个用户的教程数量。

**例 2:**

## 蟒 3

```py
from pymongo import MongoClient 

# creation of MongoClient 
client=MongoClient() 

# Connect with the portnumber and host 
client = MongoClient("mongodb://localhost:27017/") 

# Access database 
mydatabase = client['database4'] 

# Access collection of the database 
mycollection=mydatabase['myTable'] 
writer_profiles = [
    {"_id":1, "user":"Amit", "title":"Python", "comments":8},
    {"_id":2, "user":"Drew",  "title":"JavaScript", "comments":15},
    {"_id":3, "user":"Amit",  "title":"C++", "comments":6},
    {"_id":4, "user":"Drew",  "title":"MongoDB", "comments":2},
    {"_id":5, "user":"Cody",  "title":"MongoDB", "comments":16}]

mycollection.insert_many(writer_profiles)
agg_result= mycollection.aggregate(
    [{
    "$group" : 
        {"_id" : "$title",  
         "total" : {"$sum" : 1}
         }}
    ])
for i in agg_result:
    print(i)
```

**输出:**

```py
{'_id': 'MongoDB', 'total': 2}
{'_id': 'C++', 'total': 1}
{'_id': 'JavaScript', 'total': 1}
{'_id': 'Python', 'total': 1}
```

在本例中，文档按表达式 **$title** 分组，字段**总计**包括累加器运算符 **$sum** ，用于计算每个标题的文章数量。
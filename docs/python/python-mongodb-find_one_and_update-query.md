# Python MongoDB–find _ one _ and _ update 查询

> 原文:[https://www . geesforgeks . org/python-MongoDB-find _ one _ and _ update-query/](https://www.geeksforgeeks.org/python-mongodb-find_one_and_update-query/)

函数`find_one_and_update()`实际上查找并更新一个 [MongoDB](https://www.geeksforgeeks.org/mongodb-and-python/) 文档。虽然默认情况下，该函数以原始形式返回文档，但要返回更新的文档`return_document`，必须在代码中实现。

> **语法:** coll.find_one_and_update(筛选、更新、选项)
> 
> **参数:**
> 
> *   MongoDB 中的列集合
> *   过滤器-查找需要更新的文档的标准
> *   更新-更新文档需要执行的操作
> *   选项-这里可以使用投影或向上投影
> *   投影-一种映射，告知哪些字段被包含和排除，包含字段为 1/真，排除字段为 0/假
> *   向上插入-如果没有找到符合上述条件的文件，则插入新文档。向上插入为真

**例 1:**

**样本数据库:**

![python-mongodb-sample-database3](img/3e4740b76e811de5e6d3c8fede6bad4f.png)

```
from pymongo import MongoClient
from pymongo import ReturnDocument

# Create a pymongo client
client = MongoClient('localhost', 27017)

# Get the database instance
db = client['GFG']

# Create a collection
doc = db['Student']

print(doc.find_one_and_update({'name':"Raju"},
                        { '$set': { "Branch" : 'ECE'} }, 
                        return_document = ReturnDocument.AFTER))
```

**输出:**

> {“_ id”:5，“名称”:“Raju”，“Roll No”:“1005”，“Branch”:“ECE”}

**例 2:**

```
from pymongo import MongoClient
from pymongo import ReturnDocument

# Create a pymongo client
client = MongoClient('localhost', 27017)

# Get the database instance
db = client['GFG']

# Create a collection
doc = db['Student']

print(# Increasing marks of Ravi by 10 
doc.find_one_and_update({'name': "Raju"}, 
                        { '$set': { "Branch" : 'CSE'} }, 
                        projection = { "name" : 1, "Branch" : 1 }, 
                        return_document = ReturnDocument.AFTER))
```

**输出:**

```
{'_id': 5, 'name': 'Raju', 'Branch': 'CSE'}

```
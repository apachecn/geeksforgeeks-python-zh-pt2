# python mongob–distinct()

> 原文:[https://www.geeksforgeeks.org/python-mongodb-distinct/](https://www.geeksforgeeks.org/python-mongodb-distinct/)

MongoDB 是一个跨平台、面向文档的数据库，致力于集合和文档的概念。它以键值对的形式存储数据，是一个 NoSQL 数据库程序。NoSQL 这个术语的意思是非关系的。参考 [MongoDB 和 Python](https://www.geeksforgeeks.org/mongodb-and-python/) 对主题进行深入介绍。现在我们来了解一下 **distinct()** 函数在 PyMongo 中的用法。

## distinct()

PyMongo 包含`**distinct()**` 函数，该函数在单个集合中查找并返回指定字段的不同值，并在数组中返回结果。

> **语法:** distinct(键，过滤器=无，会话=无，**kwargs)
> **参数:**
> 
> *   **键:**需要找到不同值的字段名。
> *   **过滤器:**(可选)指定从中检索不同值的文档的查询文档。
> *   **会话:**(可选)客户端会话。

让我们创建一个示例集合:

```
# importing the module
from pymongo import MongoClient

# creating a MongoClient object 
client = MongoClient() 

# connecting with the portnumber and host 
client = MongoClient("mongodb://localhost:27017/") 

# accessing the database 
database = client['database'] 

# access collection of the database 
mycollection = mydatabase['myTable'] 

documents = [{"_id": 1, "dept": "A",
                  "item": {"code": "012", "color": "red"},
                  "sizes": ["S", "L"]},
             {"_id": 2, "dept": "A",
                  "item": {"code": "012", "color": "blue"},
                  "sizes": ["M", "S"]},
             {"_id": 3, "dept": "B",
                  "item": {"code": "101", "color": "blue"},
                  "sizes": "L"},
             {"_id": 4, "dept": "A",
                  "item": {"code": "679", "color": "black"},
                  "sizes": ["M"]}]

mycollection.insert_many(documents)
for doc in mycollection.find({}):
    print(doc)
```

**输出:**

```
{'_id': 1, 'dept': 'A', 'item': {'code': '012', 'color': 'red'}, 'sizes': ['S', 'L']}
{'_id': 2, 'dept': 'A', 'item': {'code': '012', 'color': 'blue'}, 'sizes': ['M', 'S']}
{'_id': 3, 'dept': 'B', 'item': {'code': '101', 'color': 'blue'}, 'sizes': 'L'}
{'_id': 4, 'dept': 'A', 'item': {'code': '679', 'color': 'black'}, 'sizes': ['M']}

```

现在我们会；使用`distinct()`方法:

*   为字段返回不同的值
*   为嵌入字段返回不同的值
*   返回数组字段的不同值
*   返回特定查询

```
# distinct() function returns the distinct values for the
# field dept from all documents in the mycollection collection
print(mycollection.distinct('dept'))

# distinct values for the field color, 
# embedded in the field item, from all documents
# in the mycollection collection
print(mycollection.distinct('item.color'))

# returns the distinct values for the field sizes 
# from all documents in the mycollection collection
print(mycollection.distinct("sizes"))

# distinct values for the field code, 
# embedded in the field item, from the documents 
# in mycollection collection whose dept is equal to B.
print(mycollection.distinct("item.code", {"dept" : "B"}))
```

`Output :`

```
['A', 'B']
['red', 'blue', 'black']
['L', 'S', 'M']
['101']

```
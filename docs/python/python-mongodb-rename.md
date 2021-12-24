# python mongbod-rename()

> 原文:[https://www.geeksforgeeks.org/python-mongodb-rename/](https://www.geeksforgeeks.org/python-mongodb-rename/)

MongoDB 是一个跨平台、面向文档的数据库，致力于集合和文档的概念。它以键值对的形式存储数据，是一个 NoSQL 数据库程序。NoSQL 这个术语的意思是非关系的。请参考 [MongoDB 和 Python](https://www.geeksforgeeks.org/mongodb-and-python/) 对该主题进行深入介绍。现在我们来了解一下`**rename()**`函数在 PyMongo 中的使用。

## 重命名()

PyMongo 函数 **`rename()`** 用于重命名集合。如果新名称不是 basestring 的实例或集合名称无效，重命名操作将失败。

> **语法:**重命名(new_name，session = None，**kwargs)
> **参数:**
> 
> *   **new_name :** 集合的新名称。
> *   **会话:**(可选)客户端会话。
> *   ****kwargs :** (可选)重命名命令的附加参数可以作为关键字参数传递给此帮助器方法(即 dropTarget = True)。

**示例 1 :** 在本例中，我们将创建一个集合并对其进行重命名。`rename()`功能将集合名称从集合重命名为 collec。`dropTarget`的值设置为真，这意味着如果现有的集合集合存在，那么新的集合将覆盖现有集合的数据。

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
collection = database['myTable'] 
docs = [{"id":1, "name":"Drew"},
        {"id":3, "name":"Cody"}]
collection.insert_many(docs)

# renaming the collection
collection.rename('collec', dropTarget = True)

result = database.collection_names()
for collect in result:
    print(collect)
```

**输出-**

```
collec

```

**示例 2 :** 在本例中，`dropTarget`参数设置为 False，输入的新集合名称应该是唯一的。但是由于集合名称 collec 已经存在于数据库中，它将返回一个错误。

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
mycollection = database['myTable'] 
docs = [{"id":1, "name":"Drew"},
        {"id":3, "name":"Cody"}]
mycollection.insert_many(docs)

# renaming the collection
mycollection.rename('collec', dropTarget = False)

result = database.collection_names()
for collect in result:
    print(collect)
```

**输出:**

```
pymongo.errors.OperationFailure: target namespace exists

```
# Python MongoDB–bulk _ write()

> 原文:[https://www.geeksforgeeks.org/python-mongodb-bulk_write/](https://www.geeksforgeeks.org/python-mongodb-bulk_write/)

MongoDB 是一个面向文档的开源数据库。MongoDB 以键值对的形式存储数据，是一个 NoSQL 数据库程序。NoSQL 这个术语的意思是非关系的。更多关于 MongoDB 的详细介绍，请参考 [MongoDB:简介](https://www.geeksforgeeks.org/mongodb-an-introduction/)。现在让我们了解一下使用 Python 在 MongoDB 中的批量写入操作。

## 批量写入()

PyMongo 函数`**bulk_write()**`向服务器发送一批写操作。批量执行写操作会增加写吞吐量。

> **语法:**批量写(请求，有序=真，旁路 _ 文档 _ 验证=假，会话=无)
> **参数:**
> 
> *   **请求:**请求作为写操作实例列表传递。
> *   **有序:**(可选)一个布尔值，指定操作执行是以有序方式还是无序方式执行。默认情况下，它设置为“真”。
> *   **旁路 _ 文档 _ 验证:**(可选)表示是否旁路文档验证的值。
> *   **会话:**(可选)客户端会话。

**示例 1 :** 使用`bulk_write()`执行多个请求。

```py
# importing the module
from pymongo import MongoClient, InsertOne, DeleteOne, ReplaceOne

# creating a MongoClient object 
client = MongoClient() 

# connecting with the portnumber and host 
client = MongoClient("mongodb://localhost:27017/") 

# accessing the database 
database = client['database']   

# access collection of the database 
mycollection = mydatabase['myTable'] 

# defining the requests
requests = [InsertOne({"Student name": "Cody"}),
            InsertOne({ "Student name": "Drew"}),
            DeleteOne({"Student name": "Cody"}),
            ReplaceOne({"Student name": "Drew"},
                       { "Student name": "Andrew"}, upsert = True)]

# executing the requests
result = mycollection.bulk_write(requests)

for doc in mycollection.find({}):
    print(doc)
```

这里，前两个文档是使用 **InsertOne 命令插入的。**然后使用**删除一个**命令，删除学生名为****科迪**的文档。使用 **ReplaceOne** 命令，名为 **Drew** 的学生被名为 **Andrew 的学生替换。**因此，所有这些命令都按顺序执行，我们得到如下输出:**

****输出:****

> **{ ' _ id ':ObjectId(' 5f 060 aa 5a 9666 ECD 86 F5 b6bd ')，'学生姓名':' Andrew'}**

****例 2 :****

```py
# importing the modules
from pymongo import MongoClient, InsertOne, DeleteOne, ReplaceOne, UpdateOne

# creating a MongoClient object 
client = MongoClient() 

# connecting with the portnumber and host 
client = MongoClient("mongodb://localhost:27017/") 

# accessing the database 
database = client['database']   

# access collection of the database 
mycollection = mydatabase['myTable']  

# defining the requests
requests = [InsertOne({ "x": 5}),
            InsertOne({ "y": 2}),
            UpdateOne({'x': 5}, {'$inc': {'x': 3}}),
            DeleteOne({ "y": 2})]

# executing the requests
result = mycollection.bulk_write(requests)

for doc in mycollection.find({}):
    print(doc)
```

**这里首先使用**插入一个**命令插入两个文档。然后更新值为 **x 等于 5** 的文档，其值增加 3。最后用**删除一个**命令删除包含 **y** 的文档。**

****输出:****

```py
{'_id': ObjectId('5f060cd7358fae75aad1ae94'), 'x': 8} 
```
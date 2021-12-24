# Python MongoDB–极限查询

> 原文:[https://www.geeksforgeeks.org/python-mongodb-limit-query/](https://www.geeksforgeeks.org/python-mongodb-limit-query/)

[MongoDB](https://www.geeksforgeeks.org/mongodb-and-python/) 是使用最多的数据库之一，其文档存储为集合。这些文档可以与 JSON 对象进行比较。当 MongoDB 与 Python 一起使用时，这个组合被称为 **PyMongo** 。

## 极限()

函数 `limit()`顾名思义就是限制将要返回的文档数量。参数中只有一个参数，它是一个数字，表示需要返回的文档数量。

**语法:**

```
coll.find().limit(n)
```

哪里，

*   **coll-** 集合的名称
*   **n-** 需要返回的号码

**例 1:**

**样本数据库:**

![python-mongodb-sample-database2](img/b39556ad7651c12cbf7e4f73f7267c4e.png)

```
from pymongo import MongoClient

# Create a pymongo client
client = MongoClient('localhost', 27017)

# database instance
db = client['GFG']

# collection instance
doc = db['Student']

# Retrieving first 3 documents using the
# find() and limit() methods
print("First 3 docs in the collection are: ")

for doc1 in doc.find().limit(3):
    print(doc1)
```

**输出:**

> 集合中的前 3 个单据为:
> {“_ id”:1、“名称”:“Vishwash”、“Roll No”:“1001”、“Branch”:“CSE”}
> {“_ id”:2、“名称”:“Vishesh”、“Roll No”:“1002”、“Branch”:“IT”}
> {“_ id”:3、“名称”:“Shivam”、“Roll No”:“1003”、“Branch”:“ME”}

虽然`limit()`对提取的文档数量进行了限制，但是 find()可以用于根据一些指定的标准来查找文档。

**例 2:**

```
from pymongo import MongoClient

# Create a pymongo client
client = MongoClient('localhost', 27017)

# database instance
db = client['GFG']

# collection instance
doc = db['Student']

# Printing documents of only those having
# branch as CSE and limiting the document 
# to 1
for doc1 in doc.find({'Branch': 'CSE'}).limit(1):
    print(doc1)
```

**输出:**

> {“_ id”:1，“名称”:“Vishwash”，“辊号”:“1001”，“分支”:“CSE”}

在获取所述数量的文件之前跳过一些文件`skip()`可以与`limit()`一起使用

**例 3:**

```
from pymongo import MongoClient

# Create a pymongo client
client = MongoClient('localhost', 27017)

# database instance
db = client['GFG']

# collection instance
doc = db['Student']

# Retrieving 3 documents using the
# find() and limit() methods
print("3 docs in the collection are: ")

for doc1 in doc.find().limit(3).skip(2):
    print(doc1)
```

**输出:**

> 集合中的 3 个单据为:
> {“_ id”:3、“名称”:“Shivam”、“Roll No”:“1003”、“Branch”:“ME”}
> {“_ id”:4、“名称”:“Yash”、“Roll No”:“1004”、“Branch”:“ECE”}
> {“_ id”:5、“名称”:“Raju”、“Roll No”:“1005”、“Branch”:“CSE”}
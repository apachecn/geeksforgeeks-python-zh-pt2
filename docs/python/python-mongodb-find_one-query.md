# Python MongoDB–find _ one 查询

> 原文:[https://www . geesforgeks . org/python-MongoDB-find _ one-query/](https://www.geeksforgeeks.org/python-mongodb-find_one-query/)

**先决条件:** [MongoDB Python 基础知识](https://www.geeksforgeeks.org/mongodb-and-python/)

本文重点介绍了 PyMongo 库的 **find_one()** 方法。`find_one()`用于从 MongoDB 中查找数据。

让我们从 find_one()方法开始:

1.  **Importing PyMongo Module:** Import the PyMongo module using the command:

    ```py
    from pymongo import MongoClient
    ```

    如果您的机器上尚未安装 MongoDB，您可以参考指南:[使用 Python 安装 MongoDB 的指南](https://www.geeksforgeeks.org/guide-install-mongodb-python-windows/)

2.  **创建连接:**现在我们已经导入了模块，是时候建立与 MongoDB 服务器的连接了，该服务器大概运行在端口 27017(端口号)的 localhost(主机名)上。

    ```py
    client = MongoClient(‘localhost’, 27017)
    ```

3.  **访问数据库:**由于与 MongoDB 服务器的连接已经建立。我们现在可以创建或使用现有的数据库。

    ```py
    mydatabase = client.name_of_the_database
    ```

4.  **访问集合:**我们现在使用以下语法从数据库中选择集合:

    ```py
    collection_name = mydatabase.name_of_collection
    ```

5.  **Finding in the collection:** Now we will find in the database using find_one() function. This function return only one value if the data is found in the database else it returns None. It is ideal for those situations where we need to search for the only one document.

    **语法:**

    ```py
    find_one(filter=None, *args, **kwargs)
    ```

**例 1:**

**样本数据库:**

![python-mongodb-insert-one-21](img/0daa20c70fcc0b008a964432fd006802.png)

```py
# Python program to demonstrate
# find_one() method

# Importing Library
from pymongo import MongoClient

# Connecting to MongoDB server
# client = MongoClient('host_name','port_number')
client = MongoClient('localhost', 27017)

# Connecting to the database named
# GFG
mydatabase = client.GFG

# Accessing the collection named
# gfg_collection
mycollection = mydatabase.Student

# Searching through the database
# using find_one method.
result = mycollection.find_one({"Branch":"CSE"})
print(result)
```

**输出:**

> {“_ id”:1，“名称”:“Vishwash”，“辊号”:“1001”，“分支”:“CSE”}

**例 2:**

```py
# Python program to demonstrate
# find_one() method

# Importing Library
from pymongo import MongoClient

# Connecting to MongoDB server
# client = MongoClient('host_name','port_number')
client = MongoClient('localhost', 27017)

# Connecting to the database named
# GFG
mydatabase = client.GFG

# Accessing the collection named
# gfg_collection
mycollection = mydatabase.Student

# Searching through the database
# using find_one method.
result = mycollection.find_one({"Branch":"CSE"},
                               {'_id':0, 'name':1, 'Roll No':1})
print(result)
```

**输出:**

```py
{'name': 'Vishwash', 'Roll No': '1001'}

```
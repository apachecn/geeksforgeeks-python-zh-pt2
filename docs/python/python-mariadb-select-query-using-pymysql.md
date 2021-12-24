# Python Mariadb–使用 PyMySQL 选择查询

> 原文:[https://www . geesforgeks . org/python-Maria db-select-query-using-pymysql/](https://www.geeksforgeeks.org/python-mariadb-select-query-using-pymysql/)

**马里亚数据库**是一个开源数据库管理系统和它的前身 MySQL。可以使用 **pymysql 客户端**与 MariaDB 进行交互，类似于使用 Python 的 mysql。

在本文中，我们将研究使用 *pymysql* 从数据库表中查询数据的过程。使用以下语法查询数据:

**语法:**

*   为了从表中选择特定的属性列，我们编写属性名。

```
 SELECT attr1, attr2 FROM table_name

```

*   为了从表中选择所有属性列，我们使用星号“*”符号。

```
SELECT * FROM table_name

```

**例 1 :**

## 蟒蛇 3

```
import pymysql

# Create a connection object
# IP address of the MySQL database server
Host = "localhost"  

# User name of the database server
User = "user"      

# Password for the database user
Password = ""           

database = "GFG"

conn  = pymysql.connect(host=Host, user=User, password=Password, database)

# Create a cursor object
cur  = conn.cursor()

query = f"SELECT * FROM PRODUCT"

cur.execute(query)

rows = cur.fetchall()
conn.close()

for row in rows :
    print(row)
```

**输出:**

![querying data in mariadb](img/56baa6ce3e2fb25d48fcb2ba9178f2ad.png)

代码输出

![querying data in mariadb](img/f55137d3d13942c3de89500b810d45e5.png)

SQL 输出

以上程序说明了与*马里亚数据库*的连接 *GFG* ，其中主机名为*本地主机*，用户名为“用户”，密码为“您的密码”。

**例 2 :**

## 蟒蛇 3

```
import pymysql

# Create a connection object

conn  = pymysql.connect('localhost', 'user', 'password', 'database')

# Create a cursor object
cur  = conn.cursor()

query = f"SELECT price,PRODUCT_TYPE FROM PRODUCT"

cur.execute(query)

rows = cur.fetchall()
conn.close()

for row in rows :
    print(row)
```

**输出:**

![querying data in mariadb](img/8032d078a881a40e3af44cca3f2d9126.png) ![querying data in mariadb](img/bea335f0f14c39767452600339c440bd.png)
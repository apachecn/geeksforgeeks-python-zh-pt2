# Python Mariadb–使用 PyMySQL 的 Order By 子句

> 原文:[https://www . geesforgeks . org/python-mariadb-order by 子句-use-pymysql/](https://www.geeksforgeeks.org/python-mariadb-order-by-clause-using-pymysql/)

当我们必须将 MySQL 与其他编程语言一起使用时，会用到 MySQL 客户端库。 **PyMySQL** 的工作是提供对 MySQL Driver 到所需语言的访问。因此，它在编程语言和 MySQL 服务器之间生成了一个连接。

## 排序依据条款

*OrderBy* 用于以升序或降序排列结果集。默认情况下，它总是按升序排列，除非提到“DESC”，这将按降序排列。“ASC”也可以用来明确地按升序排列。但是，通常不会这样做，因为违约已经这样做了。

**语法:**

```py
SELECT column_list
FROM table_name
ORDER BY column_name ASC|DESC;

```

以下程序将帮助您更好地理解这一点。

**正在使用的表:**

![](img/9974599b21dbe260f10c171a5c45573f.png)

**例 1:** 按**产品类型**升序排列**数据的程序**

## 蟒蛇 3

```py
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

query = f"SELECT * FROM PRODUCT ORDER BY PRODUCT_TYPE ASC"

cur.execute(query)

rows = cur.fetchall()
for row in rows :
    print(row)

conn.close()
```

**输出:**

![](img/e3f966eb53a4d51bc18c162d817b9611.png)

**例 2:** 按照**价格**降序排列**中的表格**

## 蟒蛇 3

```py
import pymysql

# Create a connection object

conn  = pymysql.connect('localhost', 'user',
                        'password', 'database')

# Create a cursor object
cur  = conn.cursor()

query = f"SELECT * FROM PRODUCT ORDER BY price DESC"

cur.execute(query)
for row in rows :
    print(row)

conn.close()
```

**输出:**

![](img/eb004acc6ed622a9e19df1acc168f687.png)

**例 3:** 按照**价格**按照**升序**排列桌子

## 蟒蛇 3

```py
import pymysql

# Create a connection object
conn  = pymysql.connect('localhost', 'user', 
                        'password', 'database')

# Create a cursor object
cur  = conn.cursor()

query = f"SELECT price,PRODUCT_TYPE FROM PRODUCT\
ORDER BY price ASC"

cur.execute(query)
for row in rows :
    print(row)

conn.close()
```

**输出:**

![](img/521c79fa03316fe9a6860298da010444.png)
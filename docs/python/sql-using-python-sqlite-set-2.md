# 使用 Python 和 SQLite 的 SQL 第 2 集

> 原文:[https://www . geesforgeks . org/SQL-using-python-SQLite-set-2/](https://www.geeksforgeeks.org/sql-using-python-sqlite-set-2/)

数据库提供了许多功能，用户可以通过这些功能在网络上轻松管理大量信息，并通过文本文件等典型文件输入和输出大量数据。SQL 是一种查询语言，在数据库中非常流行。很多网站都用 MySQL。SQLite 是一个“轻量级”版本，其语法与 SQL 非常相似。

SQLite 是一个独立、高可靠性、嵌入式、全功能、公共域的 SQL 数据库引擎。它是万维网中使用最多的数据库引擎。
Python 有一个用来访问 SQLite 数据库的库，称为 sqlite3，旨在与这个自 2.5 版本以来就包含在 Python 包中的数据库一起工作。

在本文中，我们将讨论如何使用更新和删除等命令查询数据库，以及如何通过图形可视化数据。
建议使用 Python | Set 1 进行 [SQL](https://www.geeksforgeeks.org/sql-using-python/)

**更新和删除操作**

```py
# code for update operation
import sqlite3

# database name to be passed as parameter
conn = sqlite3.connect('mydatabase.db')

# update the student record
conn.execute("UPDATE Student SET name = 'Sam' where unix='B113059'")
conn.commit()

print "Total number of rows updated :", conn.total_changes

cursor = conn.execute("SELECT * FROM Student")
for row in cursor:
   print row,

conn.close()
```

输出:

```py
Total number of rows updated : 1
(u'B113053', u'Geek', u'2017-01-11 13:53:39', 21.0), 
(u'B113058', u'Saan', u'2017-01-11 13:53:39', 21.0), 
(u'B113059', u'Sam', u'2017-01-11 13:53:39', 22.0)

```

```py
# code for delete operation
import sqlite3

# database name to be passed as parameter
conn = sqlite3.connect('mydatabase.db')

# delete student record from database
conn.execute("DELETE from Student where unix='B113058'")
conn.commit()
print "Total number of rows deleted :", conn.total_changes

cursor = conn.execute("SELECT * FROM Student")
for row in cursor:
   print row,

conn.close()
```

输出:

```py
Total number of rows deleted : 1
(u'B113053', u'Geek', u'2017-01-11 13:53:39', 21.0),
 (u'B113059', u'Sam', u'2017-01-11 13:53:39', 22.0)

```

**用户输入的数据**

```py
# code for executing query using input data
import sqlite3

# creates a database in RAM
con = sqlite3.connect(":memory:")
cur = con.cursor()
cur.execute("create table person (name, age, id)")

print ("Enter 5 students names:")
who = [raw_input() for i in range(5)]
print ("Enter their ages respectively:")
age = [int(raw_input()) for i in range(5)]
print ("Enter their ids respectively:")
p_id = [int(raw_input()) for i in range(5)]
n = len(who)

for i in range(n):

    # This is the q-mark style:
    cur.execute("insert into person values (?, ?, ?)", (who[i], age[i], p_id[i]))

    # And this is the named style:
    cur.execute("select * from person")

    # Fetches all entries from table
    print cur.fetchall()
```

输出:

```py
(u'Navin', 34, 113053)
(u'Basu', 42, 113058)
(u'Firoz', 65, 113059)
(u'Tim', 47, 113060)
(u'Varun', 54, 113061)

```

**用 SQLite 绘图**

```py
# graph visualization using matplotlib library
import matplotlib.pyplot as plt

def graph_data(p_id,age):

    # plotting the points    
    plt.plot(p_id, age, color='yellow', linestyle='dashed', linewidth = 3,
    marker='*', markerfacecolor='blue', markersize=12)

    # naming the x axis
    plt.xlabel('Persons Id')

    # naming the y axis
    plt.ylabel('Ages')

    # plt.plot(p_id,age)
    plt.show()

print ("Enter 5 students names:")
who = [raw_input() for i in range(5)]
print ("Enter their ages respectively:")
age = [int(raw_input()) for i in range(5)]
print ("Enter their ids respectively:")
p_id = [int(raw_input()) for i in range(5)]

# calling graph function
graph_data(p_id,age)
```

通过这种方式，我们可以使用 SQL 查询与数据库通信来执行这样的操作，并绘制一个有意义的图形来描绘其特征。

[使用 Python 的 SQL |集合 1](https://www.geeksforgeeks.org/sql-using-python/)
[使用 Python 的 SQL |集合 3(处理大数据)](https://www.geeksforgeeks.org/sql-using-python-set-3-handling-large-data/)
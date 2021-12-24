# Python PostgreSQL–订单依据

> 原文:[https://www.geeksforgeeks.org/python-postgresql-order-by/](https://www.geeksforgeeks.org/python-postgresql-order-by/)

在本文中，我们将讨论如何使用 python 在 PostgreSQL 中使用 order by 子句。

Order By 子句默认用于对 SELECT 子句返回的表的记录进行升序排序，但也可以使用 **asc** 关键字。如果我们想按降序排列记录，那么我们必须写 **desc** 字。

**语法:**

```
SELECT
    column1, column2, ....
FROM
    table_name
ORDER BY
    column1, colum2,.... [ASC | DESC]
```

**使用中的数据:**

![](img/690460623b4f17ec5fd6680c59b5da00.png)

首先，将所有需要的库导入工作空间，然后建立到数据库的连接。现在初始化一个游标，并传递要执行的 SQL 语句。打印生成的结果集并关闭连接。

**示例 1:** 以降序显示状态名称的 Python 代码

## 蟒蛇 3

```
# importing psycopg2 module
import psycopg2

# establishing the connection
conn = psycopg2.connect(
    database="postgres",
    user='postgres',
    password='password',
    host='localhost',
    port='5432'
)

# creating cursor object
cursor = conn.cursor()

# creating table
sql = '''CREATE TABLE Geeks(
 id  SERIAL NOT NULL,
 name varchar(20) not null,
 state varchar(20) not null
)'''
cursor.execute(sql)

# inserting values in the table
cursor.execute('''INSERT INTO Geeks(name , state) VALUES ('Babita','Bihar')''')
cursor.execute(
    '''INSERT INTO Geeks(name , state) VALUES ('Anushka','Hyderabad')''')
cursor.execute(
    '''INSERT INTO Geeks(name , state) VALUES ('Anamika','Banglore')''')
cursor.execute('''INSERT INTO Geeks(name , state) VALUES ('Sanaya','Pune')''')
cursor.execute(
    '''INSERT INTO Geeks(name , state) VALUES ('Radha','Chandigarh')''')

# query to sort table by descending order of state
sql2 = 'select * from Geeks order by state desc;'
# executing query
cursor.execute(sql2)
# fetching records
print(cursor.fetchall())

# Commit your changes in the database
conn.commit()

# Closing the connection
conn.close()
```

**输出:**

> [(4，‘Sanaya’，‘Pune’，(2，‘Anushka’，‘Hyderabad’，(5，‘Radha’，‘Chandigarh’)，(1，‘Babita’，‘Bihar’，(3，‘Anamika’，‘bang ore’)]

**示例 2:** 用于按名称升序显示极客记录的 Python 代码

## 蟒蛇 3

```
# importing psycopg2 module
import psycopg2

# establishing the connection
conn = psycopg2.connect(
    database="postgres",
    user='postgres',
    password='password',
    host='localhost',
    port='5432'
)

# creating cursor object
cursor = conn.cursor()

# creating table
sql = '''CREATE TABLE Geeks(
 id  SERIAL NOT NULL,
 name varchar(20) not null,
 state varchar(20) not null
)'''
cursor.execute(sql)

# inserting values in the table
cursor.execute('''INSERT INTO Geeks(name , state) VALUES ('Babita','Bihar')''')
cursor.execute(
    '''INSERT INTO Geeks(name , state) VALUES ('Anushka','Hyderabad')''')
cursor.execute(
    '''INSERT INTO Geeks(name , state) VALUES ('Anamika','Banglore')''')
cursor.execute('''INSERT INTO Geeks(name , state) VALUES ('Sanaya','Pune')''')
cursor.execute(
    '''INSERT INTO Geeks(name , state) VALUES ('Radha','Chandigarh')''')

# query to sort table by name
sql2 = 'select * from Geeks order by name;'
# executing query
cursor.execute(sql2)
# fetching records
print(cursor.fetchall())

# Commit your changes in the database
conn.commit()

# Closing the connection
conn.close()
```

**输出:**

> [(3，' Anamika '，' Banglore ')，(2，' Anushka '，' Hyderabad '，(1，' Babita '，' Bihar '，(5，' Radha '，' Chandigarh '，(4，' Sanaya '，' Pune')]
# Python MySQL–创建数据库

> 原文:[https://www.geeksforgeeks.org/python-mysql-create-database/](https://www.geeksforgeeks.org/python-mysql-create-database/)

Python 数据库应用编程接口是标准 Python 的数据库接口。大多数 Python 数据库接口都遵守该标准。Python 数据库支持的数据库服务器有多种，如 MySQL、牛虻、mSQL、PostgreSQL、微软 SQL Server 2000、Informix、Interbase、Oracle、Sybase 等。为了从 Python 连接到 MySQL 数据库服务器，我们需要导入 mysql.connector 接口。
**语法:**

```py
CREATE DATABASE DATABASE_NAME
```

**例:**

## 计算机编程语言

```py
# importing required libraries
import mysql.connector

dataBase = mysql.connector.connect(
  host ="localhost",
  user ="user",
  passwd ="gfg"
)

# preparing a cursor object
cursorObject = dataBase.cursor()

# creating database
cursorObject.execute("CREATE DATABASE geeks4geeks")
```
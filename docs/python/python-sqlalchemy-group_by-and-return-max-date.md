# Python SQLAlchemy–Group _ by 和最大返回日期

> 原文:[https://www . geesforgeks . org/python-sqlalchemy-group _ by-and-return-max-date/](https://www.geeksforgeeks.org/python-sqlalchemy-group_by-and-return-max-date/)

在本文中，我们将看到如何在 Python 中使用Group_by 并返回最大日期 SQLAlchemy。

## 安装 SQLAlchemy

SQLAlchemy 可通过 pip 安装包获得。

```py
pip install sqlalchemy
```

但是，如果您正在使用 flask，您可以使用它自己的 SQLAlchemy 实现。它可以通过以下方式安装–

```py
pip install flask-sqlalchemy
```

## 例子

在我们继续之前，我们需要有一个数据库和一个表来使用。对于这个例子，我们使用的是 mySQL 数据库，并且已经创建了一个**用户**表。该表有 6 列 7 条记录，如下所示。

![](img/84890cd1ac6502b83c645b59507c0e46.png)

用户表–MySQL

在上表中，我们可以看到有 3 个不同的用户，即约翰、艾玛和利亚姆。我们将根据他们的**名**和**姓**进行分组。该表有一个 **created_on** 字段，它是一个时间戳数据类型。它将用于为不同的用户选择最大日期。

### **进场:**

1.  首先，为了简单起见，我们将 sqlalchemy 库导入为 **db** 。所有 sqlalchemy 对象、方法等都将使用 db 前缀导入，以提高清晰度。
2.  然后我们创建引擎，它将作为数据库的连接来执行所有的数据库操作。
3.  创建元数据对象。元数据对象`**元数据**'包含了我们数据库的所有信息。
4.  使用元数据信息从数据库中获取**用户**表。
5.  我们现在可以编写一个 SQLAlchemy 查询来获取所需的记录。我们对**名**和**姓**字段执行 GROUP BY 操作，并在 SELECT 查询中使用 SQLalchemy 的 **`func.max()`** 函数检索最大日期。
6.  打印所有提取的记录。在输出中，我们可以看到我们只有 3 个不同的用户，所有用户对应的 **updated_on** 字段是我们在表条目中的最大日期。

### **下面是实现:**

## 计算机编程语言

```py
import sqlalchemy as db
from sqlalchemy.engine import result

# Define the Engine (Connection Object)
engine = db.create_engine(
    "mysql+pymysql://root:password@localhost/Geeks4Geeks")

# Create the Metadata Object
meta_data = db.MetaData(bind=engine)
db.MetaData.reflect(meta_data)

# Get the `users` table from the Metadata object
USERS = meta_data.tables['users']

# SQLAlchemy Query to GROUP BY and fetch MAX date
query = db.select([
    USERS.c.email,
    USERS.c.first_name,
    USERS.c.last_name,
    db.func.max(USERS.c.created_on)
]).group_by(USERS.c.first_name, USERS.c.last_name)

# Fetch all the records
result = engine.execute(query).fetchall()

# View the records
for record in result:
    print("\n", record)
```

**输出:**

![](img/968d97240b030979415f22b7ce43cd54.png)
# 使用 Python 的 SQL 集合 3(处理大数据)

> 原文:[https://www . geesforgeks . org/SQL-using-python-set-3-handling-大数据/](https://www.geeksforgeeks.org/sql-using-python-set-3-handling-large-data/)

建议使用 Python 浏览[SQL |集合 1](https://www.geeksforgeeks.org/sql-using-python/) 和使用 Python 和 SQLite 浏览[SQL |集合 2](https://www.geeksforgeeks.org/sql-using-python-sqlite-set-2/)

在以前的文章中，数据库的记录被限制在小的大小和单元组。本文将解释如何使用涵盖所有异常的模块 SQLite3 从数据库中读写大数据。
一个简单的方法是执行查询并使用 fetchall()。这一点已经在第一套中讨论过了。

*   **executescript()**
    This is a convenience method for executing multiple SQL statements at once. It executes the SQL script it gets as a parameter.

    ```py
    Syntax:sqlite3.connect.executescript(script)
    ```

    ```py
    import sqlite3

    # Connection with the DataBase
    # 'library.db'
    connection = sqlite3.connect("library.db")
    cursor = connection.cursor()

    # SQL piece of code Executed
    # SQL piece of code Executed
    cursor.executescript("""
        CREATE TABLE people(
            firstname,
            lastname,
            age
        );

        CREATE TABLE book(
            title,
            author,
            published
        );

        INSERT INTO
        book(title, author, published)
        VALUES (
            'Dan Clarke''s GFG Detective Agency',
            'Sean Simpsons',
            1987
        );
        """)

    sql = """
    SELECT COUNT(*) FROM book;"""

    cursor.execute(sql)

    # The output in fetched and returned
    # as a List by fetchall()
    result = cursor.fetchall()
    print(result)

    sql = """
    SELECT * FROM book;"""

    cursor.execute(sql)

    result = cursor.fetchall()
    print(result)

    # Changes saved into database
    connection.commit()

    # Connection closed(broken) 
    # with DataBase
    connection.close()
    ```

    **输出:**

    ```py
    [(1,)]
    [("Dan Clarke's GFG Detective Agency", 'Sean Simpsons', 1987)]

    ```

    注意:由于创建/写入数据库的权限，这段代码可能不适用于在线解释器。

*   **executemany()**
    It is often the case when, large amount of data has to be inserted into database from Data Files(for simpler case take Lists, arrays). It would be simple to iterate the code many a times than write every time, each line into database. But the use of loop would not be suitable in this case, the below example shows why. Syntax and use of executemany() is explained below and how it can be used like a loop.

    ```py
    import sqlite3

    # Connection with the DataBase
    # 'library.db'
    connection = sqlite3.connect("library.db")
    cursor = connection.cursor()

    # SQL piece of code Executed
    cursor.execute("""

        CREATE TABLE book(
            title,
            author,
            published);""")

    List = [('A', 'B', 2008), ('C', 'D', 2008),
                              ('E', 'F', 2010)]

    connection. executemany("""

        INSERT INTO 
        book(title, author, published) 
        VALUES (?, ?, ?)""", List)

    sql = """
          SELECT * FROM book;"""
    cursor.execute(sql)
    result = cursor.fetchall()
    for x in result:
        print(x)

    # Changes saved into database
    connection.commit()

    # Connection closed(broken) 
    # with DataBase
    connection.close()
    ```

    **输出:**

    ```py
    Traceback (most recent call last):
      File "C:/Users/GFG/Desktop/SQLITE3.py", line 16, in 
        List[2][3] =[['A', 'B', 2008], ['C', 'D', 2008], ['E', 'F', 2010]]
    NameError: name 'List' is not defined

    ```

    executemany()的使用可以使这段代码发挥作用。

    ```py
    import sqlite3

    # Connection with the DataBase
    # 'library.db'
    connection = sqlite3.connect("library.db")
    cursor = connection.cursor()

    # SQL piece of code Executed
    cursor.execute("""
        CREATE TABLE book(
            title,
            author,
            published);""")

    List = [('A', 'B', 2008), ('C', 'D', 2008), 
                              ('E', 'F', 2010)]

    connection. executemany("""
        INSERT INTO 
        book(title, author, published) 
        VALUES (?, ?, ?)""", List)

    sql = """
    SELECT * FROM book;"""
    cursor.execute(sql)
    result = cursor.fetchall()
    for x in result:
        print(x)

    # Changes saved into database
    connection.commit()

    # Connection closed(broken)
    # with DataBase
    connection.close()
    ```

    **输出:**

    ```py
    ('A', 'B', 2008)
    ('C', 'D', 2008)
    ('E', 'F', 2010)

    ```

*   **Fetch Large Data**

    ```py
    import sqlite3

    # Connection created with the
    # database using sqlite3.connect()
    connection = sqlite3.connect("company.db")
    cursor = connection.cursor()

    # Create Table command executed
    sql = """
            CREATE TABLE employee ( 
            ID INTEGER PRIMARY KEY, 
            fname VARCHAR(20), 
            lname VARCHAR(30), 
            gender CHAR(1), 
            dob DATE);"""
    cursor.execute(sql)

    # Single Tuple inserted
    sql = """
            INSERT INTO employee
            VALUES (1007, "Will", "Olsen", "M", "24-SEP-1865");"""
    cursor.execute(sql)

    # Multiple Rows inserted
    List = [(1008, 'Rkb', 'Boss', 'M', "27-NOV-1864"),
            (1098, 'Sak', 'Rose', 'F', "27-DEC-1864"),
            (1908, 'Royal', 'Bassen', "F", "17-NOV-1894")]

    connection. executemany(
            "INSERT INTO employee VALUES (?, ?, ?, ?, ?)", List)

    print("Method-1\n")

    # Multiple Rows fetched from
    # the Database
    for row in connection.execute('SELECT * FROM employee ORDER BY ID'):
            print (row)

    print("\nMethod-2\n")

    # Method-2 to fetch multiple
    # rows
    sql = """
            SELECT * FROM employee ORDER BY ID;"""

    cursor.execute(sql)
    result = cursor.fetchall()

    for x in result:
        print(x)

    connection.commit()
    connection.close()
    ```

    **输出:**

    ```py
    Method-1

    (1007, 'Will', 'Olsen', 'M', '24-SEP-1865')
    (1008, 'Rkb', 'Boss', 'M', '27-NOV-1864')
    (1098, 'Sak', 'Rose', 'F', '27-DEC-1864')
    (1908, 'Royal', 'Bassen', 'F', '17-NOV-1894')

    Method-2

    (1007, 'Will', 'Olsen', 'M', '24-SEP-1865')
    (1008, 'Rkb', 'Boss', 'M', '27-NOV-1864')
    (1098, 'Sak', 'Rose', 'F', '27-DEC-1864')
    (1908, 'Royal', 'Bassen', 'F', '17-NOV-1894')

    ```

    注意:由于创建/写入数据库的权限，这段代码可能不适用于在线解释器。
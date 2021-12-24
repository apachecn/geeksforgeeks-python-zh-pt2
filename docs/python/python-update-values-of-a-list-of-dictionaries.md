# Python–更新字典列表的值

> 原文:[https://www . geesforgeks . org/python-更新-字典列表的值/](https://www.geeksforgeeks.org/python-update-values-of-a-list-of-dictionaries/)

在本文中，我们将更新字典列表的值。

## 方法 1:使用[追加()](https://www.geeksforgeeks.org/append-extend-python/)功能

append 函数用于在字典列表中插入一个新值，我们将使用 [pop()](https://www.geeksforgeeks.org/python-dictionary-pop-method/) 函数来消除重复数据。

> **语法**:
> 
> *   字典[行]['键']。追加('值')
> *   字典[行]['键']。弹出(位置)
> 
> **其中:**
> 
> *   字典是字典的输入列表
> *   行是我们要更新的行
> *   值是要更新的新值
> *   键是要更新的列
> *   位置是旧值存在的地方

### Python 程序创建字典列表

## 蟒蛇 3

```
# create a list of dictionaries
# with student data
data = [
    {'name': 'sravan', 'subjects': ['java', 'python']},
    {'name': 'bobby', 'subjects': ['c/cpp', 'java']},
    {'name': 'ojsawi', 'subjects': ['iot', 'cloud']},
    {'name': 'rohith', 'subjects': ['php', 'os']},
    {'name': 'gnanesh', 'subjects': ['html', 'sql']}
]

# display first student
print(data[0])

# display all student
data
```

**输出:**

```
{'name': 'sravan', 'subjects': ['java', 'python']}
[{'name': 'sravan', 'subjects': ['java', 'python']},
 {'name': 'bobby', 'subjects': ['c/cpp', 'java']},
 {'name': 'ojsawi', 'subjects': ['iot', 'cloud']},
 {'name': 'rohith', 'subjects': ['php', 'os']},
 {'name': 'gnanesh', 'subjects': ['html', 'sql']}]
```

### 更新上述字典列表中的值

## 蟒蛇 3

```
# update first student python subject
# to html
data[0]['subjects'].append('html')
data[0]['subjects'].pop(1)

# update third student java subject
# to dbms
data[2]['subjects'].append('dbms')
data[2]['subjects'].pop(1)

# update forth student php subject
# to php-mysql
data[3]['subjects'].append('php-mysql')
data[3]['subjects'].pop(0)

# display updated list
data
```

**输出:**

```
[{'name': 'sravan', 'subjects': ['java', 'html']},
 {'name': 'bobby', 'subjects': ['c/cpp', 'java']},
 {'name': 'ojsawi', 'subjects': ['iot', 'dbms']},
 {'name': 'rohith', 'subjects': ['os', 'php-mysql']},
 {'name': 'gnanesh', 'subjects': ['html', 'sql']}]
```

## 方法二:使用 [insert()](https://www.geeksforgeeks.org/python-list-insert/) 功能

此函数用于插入基于索引的更新数据。

> **语法**:
> 
> *   字典[行]['键']。插入(索引，“值”)
> *   字典[行]['键']。弹出(位置)
> 
> **在哪里，**
> 
> *   字典是字典的输入列表
> *   行是我们要更新的行
> *   值是要更新的新值
> *   索引是要更新的位置
> *   键是要更新的列
> *   位置是旧值存在的地方

### **示例**:更新字典列表中的值的 Python 程序

## 蟒蛇 3

```
# update first student python subject
# to html
data[0]['subjects'].insert(0, 'html')
data[0]['subjects'].pop(1)

# update third student java subject
# to dbms
data[2]['subjects'].insert(0, 'dbms')
data[2]['subjects'].pop(1)

# update forth student php subject
# to php-mysql
data[3]['subjects'].insert(1, 'php-mysql')
data[3]['subjects'].pop(0)

# display updated list
data
```

**输出:**

```
[{'name': 'sravan', 'subjects': ['html', 'python']},
 {'name': 'bobby', 'subjects': ['c/cpp', 'java']},
 {'name': 'ojsawi', 'subjects': ['dbms', 'cloud']},
 {'name': 'rohith', 'subjects': ['php-mysql', 'os']},
 {'name': 'gnanesh', 'subjects': ['html', 'sql']}]
```
# Python |以不区分大小写的方式对字符串列表进行排序的方法

> 原文:[https://www . geesforgeks . org/python-不区分大小写的字符串列表排序方式/](https://www.geeksforgeeks.org/python-ways-to-sort-list-of-strings-in-case-insensitive-manner/)

给定一个字符串列表，任务是以不区分大小写的方式对字符串进行排序。下面给出了几个解决任务的方法。
**方法#1:使用 casefold()**

## 蟒蛇 3

```
# Python code to demonstrate
# to sort list of
# strings in case insensitive manner

# Initialising list
ini_list = ['akshat', 'garg', 'GeeksForGeeks', 'Alind',
            'SIngh', 'manjeet', 'Munich']

# Sorting list in case sensitive manner
res1 = sorted(ini_list)

# Printing case-insensitive
print("Case-sensitive sorted list", str(res1))

# Sorting list in case-insensitive manner
res2 = sorted(ini_list, key = lambda s: s.casefold())

# Printing result
print("Case-insensitive sorted list", str(res2))

```

**Output:** 

区分大小写的排序列表['Alind '，' GeeksForGeeks '，'慕尼黑'，' SIngh '，' akshat '，' garg '，' manjeet']
不区分大小写的排序列表['akshat '，' Alind '，' garg '，' GeeksForGeeks '，' manjeet '，'慕尼黑'，' SIngh']

**方法#2:使用 lower()**

## 蟒蛇 3

```
# Python code to demonstrate
# to sort list of
# strings in case insensitive manner

# Initialising list
ini_list = ['akshat', 'garg', 'GeeksForGeeks', 'Alind',
            'SIngh', 'manjeet', 'Munich']

# Sorting list in case sensitive manner
ini_list.sort()

# Printing case-insensitive
print("Case-sensitive sorted list", str(ini_list))

# Sorting list in case-insensitive manner
ini_list.sort(key = lambda x: x.lower())

# Printing result
print("Case-insensitive sorted list", str(ini_list))

```

**Output:** 

区分大小写的排序列表['Alind '，' GeeksForGeeks '，'慕尼黑'，' SIngh '，' akshat '，' garg '，' manjeet']
不区分大小写的排序列表['akshat '，' Alind '，' garg '，' GeeksForGeeks '，' manjeet '，'慕尼黑'，' SIngh']
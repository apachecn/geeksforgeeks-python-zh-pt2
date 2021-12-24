# Python |按照给定字典的字母顺序对项目进行排序

> 原文:[https://www . geesforgeks . org/python-按给定字典的字母顺序对项目进行排序/](https://www.geeksforgeeks.org/python-sort-the-items-alphabetically-from-given-dictionary/)

给定一个字典，编写一个 Python 程序，从给定的字典中获取按字母顺序排序的项目并打印出来。让我们看看有什么方法可以完成这项任务。

**代码#1:** 使用字典项目()

```
# Python program to sort the items alphabetically from given dictionary

# initialising _dictionary 
dict = {'key1' : 'AGeek', 'key2' : 'For', 'key3': 'IsGeeks',  'key4': 'ZGeeks'} 

# printing iniial_dictionary 
print ("Original dictionary", str(dict)) 

# getting items in sorted order 
print ("\nItems in sorted order") 
for key, value in sorted(dict.items()): 
    print(value) 
```

**输出:**

> 原始词典{'key4': 'ZGeeks '，' key2': 'For '，' key1': 'AGeek '，' key3': 'IsGeeks'}
> 
> 按排序顺序排列的物品
> T2 的物品
> 是极客的物品

**代码#2:** 使用排序的()

```
# Python program to sort the items alphabetically from given dictionary

# initialising _dictionary 
dict = {'key1' : 'AGeek', 'key2' : 'For', 'key3': 'IsGeeks',  'key4': 'ZGeeks'} 

# printing iniial_dictionary 
print ("Original dictionary", str(dict)) 

# getting items in sorted order 
print ("\nItems in sorted order") 
for key in sorted(dict): 
    print (dict[key]) 
```

**输出:**

> 原始词典{'key4': 'ZGeeks '，' key2': 'For '，' key1': 'AGeek '，' key3': 'IsGeeks'}
> 
> 按排序顺序排列的物品
> T2 的物品
> 是极客的物品
# Python 程序根据键长对字典进行排序

> 原文:[https://www . geesforgeks . org/python-程序-按键长度排序-字典/](https://www.geeksforgeeks.org/python-program-to-sort-dictionary-by-key-lengths/)

给定字典，按其键长排序。

> **输入**:test _ dict = {“Gfg”:4、“is”:1、“best”:0、“for”:3、“极客”:3}
> **输出**:{“is”:1、“Gfg”:4、“for”:3、“best”:0、“极客”:3}
> **解释** : 2 < 3 = 3 < 4 < 5，均按长度顺序排序。
> 
> **输入**:test _ dict = {“Gfg”:4、“for”:3、“极客”:3}
> **输出**:{“Gfg”:4、“for”:3、“极客”:3}
> **解释** : 3 = 3 < 5，都是按长度顺序排序的。

**方法一:使用 len() + sort() +词典理解+ items()**

在本例中，我们使用 sort()执行排序任务，items()用于从字典中获取元组对，len()获取键长度。然后词典理解执行转换回词典的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Dictionary by Key Lengths
# Using len() + sort() + dictionary comprehension + items()

def get_len(key):
    return len(key[0])

# initializing dictionary
test_dict = {"Gfg" : 4, "is" : 1, "best" : 0, "for" : 3, "geeks" : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# sorting using sort()
# external to render logic 
test_dict_list = list(test_dict.items())
test_dict_list.sort(key = get_len)

# reordering to dictionary
res = {ele[0] : ele[1]  for ele in test_dict_list}

# printing result 
print("The sorted dictionary : " + str(res)) 
```

**输出:**

> 原始字典为:{'Gfg': 4，' is': 1，' best': 0，' for': 3，' geeks': 3}
> 排序字典为:{'is': 1，' Gfg': 4，' for': 3，' best': 0，' geeks': 3}

**方法二:使用排序()+ lambda 函数+ items() +字典理解**

在本文中，我们使用 sorted()执行排序任务，lambda 函数用于提供获取键长度的逻辑。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Dictionary by Key Lengths
# Using sorted() + lambda function + items() + dictionary comprehension

# initializing dictionary
test_dict = {"Gfg" : 4, "is" : 1, "best" : 0, "for" : 3, "geeks" : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# sorting using sorted()
# lambda fnc. to render logic 
test_dict_list = sorted(list(test_dict.items()), key = lambda key : len(key[0]))

# reordering to dictionary
res = {ele[0] : ele[1]  for ele in test_dict_list}

# printing result 
print("The sorted dictionary : " + str(res)) 
```

**输出:**

> 原始字典为:{'Gfg': 4，' is': 1，' best': 0，' for': 3，' geeks': 3}
> 排序字典为:{'is': 1，' Gfg': 4，' for': 3，' best': 0，' geeks': 3}
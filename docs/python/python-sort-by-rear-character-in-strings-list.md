# Python–按字符串列表中的后字符排序

> 原文:[https://www . geesforgeks . org/python-按字符串中的后字符排序-列表/](https://www.geeksforgeeks.org/python-sort-by-rear-character-in-strings-list/)

给定一个字符串列表，按照字符串列表中的最后一个字符进行排序。

> **输入** : test_list = ['gfg '，' is '，' for '，'极客']
> **输出** : ['gfg '，' for '，' is '，'极客']
> **解释** : g < r < s = s，遂序。
> 
> **输入** : test_list = ['gfz '，' is '，' for '，'极客']
> **输出** : ['for '，' is '，'极客'，' gfz']
> **解释** : r < s = s < z，遂序。

**方法#1:使用 sort()**

在本例中，我们使用 sort()执行排序任务，外部函数用于获取字符串中的后元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort by Rear Character in Strings List
# Using sort()

# sort key function
def get_rear(sub):
    return sub[-1]

# initializing list
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# using sort with key fnc.
# performs inplace sort
test_list.sort(key = get_rear)

# printing result
print("Sorted List : " + str(test_list))
```

**Output**

```
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
Sorted List : ['gfg', 'for', 'is', 'geeks', 'best']
```

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)

在本文中，我们使用 sorted()来执行 sort，explicit，并使用 lambda 函数来执行获取尾部元素的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort by Rear Character in Strings List
# Using sorted() + lambda

# initializing list
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# lambda function for rear element
# performs non-inplace sort
res = sorted(test_list, key = lambda sub : sub[-1])

# printing result
print("Sorted List : " + str(res))
```

**Output**

```
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
Sorted List : ['gfg', 'for', 'is', 'geeks', 'best']
```
# Python–基于反向字符串的排序

> 原文:[https://www . geesforgeks . org/python-基于反向字符串排序/](https://www.geeksforgeeks.org/python-sort-on-basis-of-reverse-strings/)

给定一个字符串列表，根据字符串的逆序对列表进行排序。

> **输入**:test _ list =【“gfg”、“is”、“best”、“geeks”】
> **输出**:【‘gfg’、‘is’、‘geeks’、‘best’】
> **解释** : g <是< ks < t【元素从后方来】，遂为顺序。
> 
> **输入**:test _ list =[“gfg”、“is”、“best”]
> **输出**:[‘gfg’、‘is’、‘best’]
> **解释** : g < s < t【元素来自后方】，遂为顺序。

**方法#1:使用 sort() + reverse()**

这是执行这项任务的方法之一。在这种情况下，我们首先反转每个元素，执行排序，然后再次反转每个字符串以获得结果排序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort on basis of reverse Strings
# Using reverse() + sort()

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks"]

# printing original list
print("The original list : " + str(test_list))

# reverse() to reverse each string 
res = []
for ele in test_list:
    res.append("".join(reversed(ele))) 

# sorting to get required ordering 
res.sort()

# reverse each element again
test_list = []
for ele in res:
    test_list.append("".join(reversed(ele))) 

# printing result 
print("List after sorting on reversed strings : " + str(test_list))
```

**Output**

```py
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
List after sorting on reversed strings : ['gfg', 'for', 'is', 'geeks', 'best']

```

**方法 2:使用列表切片+排序()**

这是执行这项任务的另一种方式。在这个列表中，切片用于执行反向操作，sort()用于排序，在一个行中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort on basis of reverse Strings
# Using list slicing + sort()

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks"]

# printing original list
print("The original list : " + str(test_list))

# [::-1] to reverse each string 
# sort() to sort
test_list.sort(key = lambda sub: sub[::-1])

# printing result 
print("List after sorting on reversed strings : " + str(test_list))
```

**Output**

```py
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
List after sorting on reversed strings : ['gfg', 'for', 'is', 'geeks', 'best']

```
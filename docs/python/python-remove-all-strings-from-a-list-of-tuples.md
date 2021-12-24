# Python |从元组列表中移除所有字符串

> 原文:[https://www . geesforgeks . org/python-从元组列表中移除所有字符串/](https://www.geeksforgeeks.org/python-remove-all-strings-from-a-list-of-tuples/)

给定包含整数和字符串的元组列表，任务是从元组列表中移除所有字符串。

**示例:**

```
Input : [(1, 'Paras'), (2, 'Jain'), (3, 'GFG'), (4, 'Cyware')]
Output :   [(1), (2), (3), (4)]

Input : [('string', 'Geeks'), (2, 225), (3, '111')]
Output : [(), (2, 225), (3,)]

```

**方法#1:** 使用过滤器()方法

```
# Python code to remove all strings from a list of tuples

# Check function to check isinstance
def check(x):
    return not isinstance(x, str)

# creating list of tuples
listOfTuples = [('string', 'Paras'), (2, 'Jain'), (3, 'GFG'),
                                 (4, 'Cyware'), (5, 'Noida')]    

# using filter 
output = ([tuple(filter(check, x)) for x in listOfTuples])

# printing output
print(output)
```

**Output:**

```
[(), (2,), (3,), (4,), (5,)]

```

**方法 2:**

```
# Python code to remove all strings from a list of tuples

# Creating list of tuples
listOfTuples = [('string', 'Geeks'), (2, 225), (3, '111'),
                                 (4, 'Cyware'), (5, 'Noida')]    

output = [tuple(j for j in i if not isinstance(j, str))
                                 for i in listOfTuples]

# printing output
print(output)
```

**Output:**

```
[(), (2, 225), (3,), (4,), (5,)]

```
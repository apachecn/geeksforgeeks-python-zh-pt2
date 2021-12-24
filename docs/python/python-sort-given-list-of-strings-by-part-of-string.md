# Python |按字符串的一部分对给定的字符串列表进行排序

> 原文:[https://www . geeksforgeeks . org/python-按字符串的一部分排序给定字符串列表/](https://www.geeksforgeeks.org/python-sort-given-list-of-strings-by-part-of-string/)

给定一个字符串列表，任务是根据字符串中由某个字符分隔的部分对列表进行排序。在这个场景中，我们考虑用空格分隔字符串，这意味着它必须按每个字符串的第二部分排序。

下面给出了一些解决给定任务的方法。

**方法一:使用*排序*T3**

```
# Python code to demonstrate to sort list 
# containing string by part of string

# Initialising list
ini_list = ["GeeksForGeeks abc", "manjeet xab", "akshat bac"]

# printing initial list
print ("initial list", str(ini_list))

# code to sort list
ini_list.sort(key = lambda x: x.split()[1])

# printing result
print ("result", str(ini_list))
```

**Output:**

```
initial list ['GeeksForGeeks abc', 'manjeet xab', 'akshat bac']
result ['GeeksForGeeks abc', 'akshat bac', 'manjeet xab']

```

**方法 2:使用*排序***

```
# Python code to demonstrate to sort list 
# containing string by part of string

# Initialising list
ini_list = ["GeeksForGeeks abc", "manjeet xab", "akshat bac"]

# printing initial list
print ("initial list", str(ini_list))

# code to sort list
res = sorted(ini_list, key = lambda x: x.split()[1])

# printing result
print ("result", res)
```

**Output:**

```
initial list ['GeeksForGeeks abc', 'manjeet xab', 'akshat bac']
result ['GeeksForGeeks abc', 'akshat bac', 'manjeet xab']

```
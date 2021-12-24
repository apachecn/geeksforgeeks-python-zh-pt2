# 在字典中交换键值的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序到交换-字典中的键和值/](https://www.geeksforgeeks.org/python-program-to-swap-keys-and-values-in-dictionary/)

[字典](https://www.geeksforgeeks.org/python-dictionary/)是编程中相当有用的一种数据结构，通常用于用值对特定的键进行散列，以便可以高效地检索它们。

让我们讨论在 Python 字典中交换键和值的各种方法。

**方法#1(当有多个相同的值时不起作用):**
一个简单的解决方案可能是分别交换键和值。
**例:**

> **输入:**{“A”:67，“B”:23，“C”:45，“D”:56，“E”:12，“F”:69，“G”:67，“H”:23 }
> **输出:**{ 67:“G”，69:“F”，23:“H”，56:“D”，12:“E”，45:“C”}

```py
# Python3 code to demonstrate  
# swap of key and value 

# initializing dictionary 
old_dict = {'A': 67, 'B': 23, 'C': 45, 'D': 56, 'E': 12, 'F': 69, 'G': 67, 'H': 23}

new_dict = dict([(value, key) for key, value in old_dict.items()])

# Printing original dictionary 
print ("Original dictionary is : ")
print(old_dict) 

print()

# Printing new dictionary after swapping keys and values
print ("Dictionary after swapping is :  ") 
print("keys: values")
for i in new_dict:
    print(i, " :  ", new_dict[i])
```

**输出**

```py
Original dictionary is : 
{'D': 56, 'E': 12, 'C': 45, 'A': 67, 'F': 69, 'H': 23, 'B': 23, 'G': 67}

Dictionary after swapping is :  
keys: values
67  :   G
69  :   F
23  :   B
56  :   D
12  :   E
45  :   C

```

但是这种方法有一个问题。在我们的示例中，我们有多个具有相同值的键(即‘A’，67)和(‘G’，67)，其他具有相同值的键是(‘B’，23)和(‘H’，23)。
但是在结果中我们只从每个中获得了一个键。
即我们只获得了(' G '，67)和(' B '，23)。

所以，这里有另一种方法来处理这个问题:

**方法#2(处理多个相同的值):**
在这种方法中，我们将检查值是否已经存在。如果有的话，就把它添加到列表中。

**示例:**

> **输入:** {'A': 67，' B': 23，' C': 45，' E': 12，' F': 69，' G': 67，' H': 23}
> **输出:** {45: ['C']，67: ['A '，' G']，12: ['E']，69: ['F']，23: ['B '，' H']

```py
# Python3 code to demonstrate  
# swap of key and value 

# initializing dictionary 
old_dict = {'A': 67, 'B': 23, 'C': 45, 'E': 12, 'F': 69, 'G': 67, 'H': 23}

# Printing original dictionary 
print ("Original dictionary is : ")
print(old_dict) 

print()
new_dict = {}
for key, value in old_dict.items():
   if value in new_dict:
       new_dict[value].append(key)
   else:
       new_dict[value]=[key]

# Printing new dictionary after swapping
# keys and values
print ("Dictionary after swapping is :  ") 
print("keys: values")
for i in new_dict:
    print(i, " :", new_dict[i])
```

**输出**

```py
Original dictionary is : 
{'F': 69, 'G': 67, 'H': 23, 'A': 67, 'C': 45, 'B': 23, 'E': 12}

Dictionary after swapping is :  
keys: values
45  : ['C']
67  : ['G', 'A']
12  : ['E']
69  : ['F']
23  : ['H', 'B']

```
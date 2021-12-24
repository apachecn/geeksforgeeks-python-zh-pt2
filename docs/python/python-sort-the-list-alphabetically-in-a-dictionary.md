# Python |在字典中按字母顺序对列表进行排序

> 原文:[https://www . geesforgeks . org/python-按字典字母顺序对列表进行排序/](https://www.geeksforgeeks.org/python-sort-the-list-alphabetically-in-a-dictionary/)

在 Python 中[字典](https://www.geeksforgeeks.org/python-dictionary/)是一个相当有用的数据结构，它通常用于散列具有*值*的特定键，以便可以高效地检索它们。

让我们看看如何在字典中按字母顺序排列列表。

**示例#1:**

```py
# Python program to sort the list 
# alphabetically in a dictionary
dict ={
    "L1":[87, 34, 56, 12],
    "L2":[23, 00, 30, 10],
    "L3":[1, 6, 2, 9],
    "L4":[40, 34, 21, 67]
}

print("\nBefore Sorting: ")
for x in dict.items():
    print(x)

print("\nAfter Sorting: ")

for i, j in dict.items():
    sorted_dict ={i:sorted(j)}
    print(sorted_dict)
```

**Output:**

```py
Before Sorting: 
('L2', [23, 0, 30, 10])
('L3', [1, 6, 2, 9])
('L4', [40, 34, 21, 67])
('L1', [87, 34, 56, 12])

After Sorting: 
{'L2': [0, 10, 23, 30]}
{'L3': [1, 2, 6, 9]}
{'L4': [21, 34, 40, 67]}
{'L1': [12, 34, 56, 87]}

```

**例 2:**

```py
# Python program to sort the list 
# alphabetically in a dictionary

dict ={
    "L1":["Geeks", "for", "Geeks"],
    "L2":["A", "computer", "science"],
    "L3":["portal", "for", "geeks"],
}

print("\nBefore Sorting: ")
for x in dict.items():
    print(x)

print("\nAfter Sorting: ")
for i, j in dict.items():
    sorted_dict ={i:sorted(j)}
    print(sorted_dict)
```

**Output:**

```py
Before Sorting: 
('L3', ['portal', 'for', 'geeks'])
('L1', ['Geeks', 'for', 'Geeks'])
('L2', ['A', 'computer', 'science'])

After Sorting: 
{'L3': ['for', 'geeks', 'portal']}
{'L1': ['Geeks', 'Geeks', 'for']}
{'L2': ['A', 'computer', 'science']}

```

**例 3:**

```py
# Python program to sort the list 
# alphabetically in a dictionary
dict={
    "L1":[87,34,56,12],
    "L2":[23,00,30,10],
    "L3":[1,6,2,9],
    "L4":[40,34,21,67]
}

print("\nBefore Sorting: ")
for x in dict.items():
    print(x)

sorted_dict = {i: sorted(j) for i, j in dict.items()}
print("\nAfter Sorting: ", sorted_dict)
```

**Output:**

```py
Before Sorting: 
('L1', [87, 34, 56, 12])
('L2', [23, 0, 30, 10])
('L3', [1, 6, 2, 9])
('L4', [40, 34, 21, 67])

After Sorting:  {'L1': [12, 34, 56, 87], 
                 'L2': [0, 10, 23, 30],
                 'L3': [1, 2, 6, 9], 
                 'L4': [21, 34, 40, 67]}

```
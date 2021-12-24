# Python |从给定的元组列表中删除具有重复第一个值的元组

> 原文:[https://www . geesforgeks . org/python-remove-tuples-having-replicate-first-value-from-给定的元组列表/](https://www.geeksforgeeks.org/python-remove-tuples-having-duplicate-first-value-from-given-list-of-tuples/)

给定元组列表，任务是从给定元组列表中移除所有具有重复第一值的元组。

**示例:**

```py
Input:  [(12.121, 'Tuple1'), (12.121, 'Tuple2'), 
         (12.121, 'Tuple3'), (923232.2323, 'Tuple4')]
Output:  [(12.121, 'Tuple1'), (923232.2323, 'Tuple4')]

Input:  [('Tuple1', 121), ('Tuple2', 125), 
         ('Tuple1', 135), ('Tuple4', 478)]
Output:  [('Tuple1', 121), ('Tuple2', 125), ('Tuple4', 478)]
```

以下是实现上述任务的一些方法。

**方法#1:使用迭代**

```py
# Python code to remove tuples having 
# duplicate first value from given
# list of tuples

# Input list initialization
Input = [(12.121, 'Geeksforgeeks is best'), 
         (19212.22, 'India is best'), 
         (12.121, 'Cyware is best.'),
         (923232.2323, 'Jiit is best')]

# using set
visited = set()

# Output list initialization
Output = []

# Iteration
for a, b in Input:
    if not a in visited:
        visited.add(a)
        Output.append((a, b))

# Printing
print("Initial list of tuple is \n", Input)
print("List of tuple after removing duplicates:\n ", Output)
```

**Output:**

> 元组的初始列表为
> [(12.121，Geeksforgeeks 最好’)，(19212.22，‘印度最好’)，(12.121，Cyware 最好。’)，(923232.2323，Jiit 最好’)]
> 
> 删除重复项后的元组列表:
> [(12.121，Geeksforgeeks 最好’)，(19212.22，India 最好’)，(923232.2323，Jiit 最好’)]

**方法二:使用列表理解**

```py
# Python code to remove tuples having 
# duplicate first value from given
# list of tuples

# Input list initialization
Input = [(12.121, 'Geeksforgeeks is best'), 
         (19212.22, 'India is best'), 
         (19212.22, 'Cyware is best.'), 
         (923232.2323, 'Jiit is best')]

# Using set
seen = set()

# using list comprehension
Output = [(a, b) for a, b in Input 
         if not (a in seen or seen.add(a))]

# Printing
print("Initial list of tuple is" \n, Input)
print("\nList of tuple after removing duplicates \n", Output)
```

**Output:**

> 元组的初始列表为
> [(12.121，Geeksforgeeks 最好’)，(19212.22，‘印度最好’)，(19212.22，Cyware 最好。’)，(923232.2323，Jiit 最好’)]
> 
> 删除重复项后的元组列表[(12.121，Geeksforgeeks 最好’)，(19212.22，India 最好’)，(923232.2323，Jiit 最好’)]

**方法 3:使用迭代工具**

```py
# Python code to remove tuples having 
# duplicate first value from given
# list of tuples

import itertools

# Input list initialization
Input = [(12.121, 'Geeksforgeeks is best'), 
         (19212.22, 'India is best'), 
         (923232.2323, 'Cyware is best.'), 
         (923232.2323, 'Jiit is best')]

# Using groupby
Output = ([next(b) for a, b in itertools.groupby(
                         Input, lambda y: y[0])])

# Printing
print("Initial list of tuple is\n", Input)
print("\nList of tuple after removing duplicates\n", Output)
```

**Output:**

> 元组的初始列表为
> [(12.121，Geeksforgeeks 最好’)，(19212.22，‘印度最好’)，(923232.2323，Cyware 最好。’)，(923232.2323，Jiit 最好’)]
> 
> 删除重复项后的元组列表
> [(12.121，Geeksforgeeks 最好’)，(19212.22，‘印度最好’)，(923232.2323，Cyware 最好。’)]

**方法#4:使用 OrderedDict**

这是删除重复项最优雅的方法，即使用 OrderedDict。

```py
# Python code to remove tuples having 
# duplicate first value from given
# list of tuples

from collections import OrderedDict

# Input list initialization
Input = [(12.121, 'Geeksforgeeks is best'), 
         (19212.22, 'India is best'), 
         (19212.22, 'Cyware is best.'), 
         (923232.2323, 'Jiit is best')]

# Using orderedDIct
Output = OrderedDict(Input).items()

# Printing
print("Initial list of tuple is\n", Input)
print("\nList of tuple after removing duplicates\n", Output)
```

**Output:**

> 元组的初始列表为
> [(12.121，Geeksforgeeks 最好’)，(19212.22，‘印度最好’)，(19212.22，Cyware 最好。’)，(923232.2323，Jiit 最好’)]
> 
> 删除重复项后的元组列表
> odit _ items([(12.121，Geeksforgeeks 最好’)，(19212.22，Cyware 最好。’)，(923232.2323，Jiit 最好’)])
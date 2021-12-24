# Python |求解包含数字和算术运算符的给定列表

> 原文:[https://www . geesforgeks . org/python-求解给定列表-包含数字和算术运算符/](https://www.geeksforgeeks.org/python-solve-given-list-containing-numbers-and-arithmetic-operators/)

给定一个包含数字和算术运算符的列表，任务是求解该列表。

**示例:**

```
Input: lst =  [2, '+', 22, '+', 55, '+', 4]
Output: 83

Input: lst =  [12, '+', 8, '-', 5]
Output: 15

```

以下是实现上述任务的一些方法。

**方法#1:使用迭代**
我们可以使用迭代作为最简单的方法，通过导入不同的运算符来求解列表。

```
# Python code to solve the list
# containing numbers and arithmetic operators

# Importing
from operator import add, sub

# Function to solve list
def find(Input):
    ans = 0
    options = {'+': add, '-': sub}
    option = add 
    for item in Input:
        if item in options:
            option = options[item]
        else:
            number = float(item)
            ans = option(ans, number)
    return ans

# Input Initialization
lst = [91, '+', 132, '-', 156, '+', 4]

# Calling function
Output = find(lst)

# Printing output
print("Initial list", lst)
print("Answer after solving list is:", Output)
```

**Output:**

```
Initial list [91, '+', 132, '-', 156, '+', 4]
Answer after solving list is: 71.0

```

**方法 2:使用*评估*和*加入*T5】**

```
# Python code to solve the list
# containing numbers and arithmetic operators

# Input list initialization
lst =  [2, '+', 22, '+', 55, '+', 4]

# Using eval and join
Output = eval(' '.join(str(x) for x in lst))

# Printing output
print("Initial list", lst)
print("Answer after solving list is:", Output)
```

**Output:**

```
Initial list [2, '+', 22, '+', 55, '+', 4]
Answer after solving list is: 83

```
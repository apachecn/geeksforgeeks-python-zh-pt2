# Python |用第一个列表中相同元素的索引替换第二个列表中的元素

> 原文:[https://www . geeksforgeeks . org/python-将第二列表中的元素替换为第一列表中相同元素的索引/](https://www.geeksforgeeks.org/python-replace-elements-in-second-list-with-index-of-same-element-in-first-list/)

给定两个字符串列表，其中第一个列表包含第二个列表的所有元素，任务是用第一个列表中元素的索引替换第二个列表中的每个元素。
**方法#1:使用迭代**

## 蟒蛇 3

```py
# Python code to replace every element
# in second list with index of first element.

# List Initialization
Input1 = ['cut', 'god', 'pass']
Input2 = ['god', 'cut', 'cut', 'cut',
          'god', 'pass', 'cut', 'pass']

# List Initialization
Output = []

# Using iteration
for x in Input2:
    for y in Input1:
        if x == y:
            Output.append(Input1.index(y))

# Printing output
print("initial 2 list are")
print(Input1, "\n", Input2)
print("Second list after replacement is:", Output)
```

**Output:** 

```py
initial 2 list are
['cut', 'god', 'pass'] 
 ['god', 'cut', 'cut', 'cut', 'god', 'pass', 'cut', 'pass']
Second list after replacement is: [1, 0, 0, 0, 1, 2, 0, 2]
```

**方法 2:使用列表理解**

## 蟒蛇 3

```py
# Python code to replace every element
# in second list with index of first element.

# List initialization
Input1 = ['cut', 'god', 'pass']

# using enumerate
temp = {y:x for x, y in enumerate(Input1)}

# List initialization
Input2 = ['god', 'cut', 'cut', 'cut',
          'god', 'pass', 'cut', 'pass']

# Using list comprehension
Output = [temp.get(elem) for elem in Input2]

# Printing output
print("initial 2 list are")
print(Input1, "\n", Input2)
print("Second list after replacement is:", Output)
```

**Output:** 

```py
initial 2 list are
['cut', 'god', 'pass'] 
 ['god', 'cut', 'cut', 'cut', 'god', 'pass', 'cut', 'pass']
Second list after replacement is: [1, 0, 0, 0, 1, 2, 0, 2]
```

**方法三:使用** ***地图***

## 蟒蛇 3

```py
# Python code to replace every element
# in second list with index of first element.

# List initialization
Input1 = ['cut', 'god', 'pass']

# List initialization
Input2 = ['god', 'cut', 'cut', 'cut',
          'god', 'pass', 'cut', 'pass']

elem = {k: i for i, k in enumerate(Input1)}
Output = list(map(elem.get, Input2))

# Printing output
print("initial 2 list are")
print(Input1, "\n", Input2)
print("Second list after replacement is:", Output)
```

**Output:** 

```py
initial 2 list are
['cut', 'god', 'pass'] 
 ['god', 'cut', 'cut', 'cut', 'god', 'pass', 'cut', 'pass']
Second list after replacement is: [1, 0, 0, 0, 1, 2, 0, 2]
```
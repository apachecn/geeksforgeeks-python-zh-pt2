# Python |元组的乘法元素

> 原文:[https://www . geeksforgeeks . org/python-multiple-elements of-tuple/](https://www.geeksforgeeks.org/python-multiply-elements-of-tuple/)

给定元组列表，任务是将元组的元素相乘，并返回相乘元素的列表。

示例:

> **输入:** [(2，3)，(4，5)，(6，7)，(2，8)]
> **输出:**【6，20，42，16】
> 
> **输入:** [(11，22)，(33，55)，(55，77)，(11，44)]
> **输出:**【242，1815，4235，484】

有多种方法来倍增元组的元素。让我们看几个。

**#方法 1:** 使用迭代
这是解决这个任务最幼稚的方法。在这种情况下，我们迭代整个元组列表，并将每个元组中的元素相乘，以获得元素列表。

```
# Python code to convert list of tuple into list of elements
# formed by multiplying elements of tuple.

# Input list initialisation
Input = [(2, 3), (4, 5), (6, 7), (2, 8)]

# Output list initialisation
Output = []

# Iteration to multiply element and append multiplied element in 
# new list
for elem in Input:
    temp = elem[0]*elem[1]
    Output.append(temp)

# printing output
print("The original list of tuple is ")
print(Input)

print("\nThe answer is")
print(Output)
```

**输出:**

```
The original list of tuple is 
[(2, 3), (4, 5), (6, 7), (2, 8)]

The answer is
[6, 20, 42, 16]

```

**#方法 2:** 使用列表理解
这是实现这个任务的解决方案的一条线的方法。

```
# Python code to convert list of tuple into list of elements
# formed by multiplying elements of tuple.

# Input list initialisation
Input = [(2, 3), (4, 5), (6, 7), (2, 8)]

# Iteration to multiply element and append multiplied element in 
# new list
Output = [(x * y) for x, y in Input]

# printing output
print("The original list of tuple is ")
print(Input)

print("\nThe answer is")
print(Output)
```

**输出:**

```
The original list of tuple is 
[(2, 3), (4, 5), (6, 7), (2, 8)]

The answer is
[6, 20, 42, 16]

```
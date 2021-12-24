# Python |基于和的元组排序列表

> 原文:[https://www . geesforgeks . org/python-基于元组列表的排序/sum/](https://www.geeksforgeeks.org/python-sort-list-of-tuple-based-on-sum/)

给定一个元组列表，任务是根据元组中元素的总和对元组列表进行排序。

**示例:**

> **输入:** [(4，5)，(2，3)，(6，7)，(2，8)]
> **输出:** [(2，3)，(4，5)，(2，8)，(6，7)]
> 
> **输入:** [(3，4)，(7，8)，(6，5)]
> **输出:** [(3，4)，(6，5)，(7，8)]

**#方法 1:** 使用[冒泡排序](https://www.geeksforgeeks.org/bubble-sort/)T5】使用冒泡排序的技巧来进行排序。请注意，每个元组都是给定列表中的一个元素。使用嵌套循环访问每个元组的元素。这将执行就地排序方法。时间复杂度类似于冒泡排序，即`O(n^2).`

```py
# Python code to sort list of tuple based on sum of element in tuple.

# Input list initialisation
Input = [(4, 5), (2, 3), (6, 7), (2, 8)] 

print("The original list of tuple is ")
print(Input)

# getting length of list of tuples
lst = len(Input)

# Bubble sort
for i in range(lst):

    for j in range(lst-i-1):
        if (Input[j][0]+Input[j][1]) > (Input[j+1][0]+Input[j+1][1]):
            Input[j], Input[j+1] = Input[j+1], Input[j]

# print output
print("\nThe answer is")
print(Input)
```

**输出:**

```py
The original list of tuple is 
[(4, 5), (2, 3), (6, 7), (2, 8)]

The answer is
[(2, 3), (4, 5), (2, 8), (6, 7)]

```

**#方法二:**使用[排序()方法](https://www.geeksforgeeks.org/sorted-function-python/)

这是实现这一任务解决方案的最基本、最高效、最简短的方法。
在这种情况下，我们将 lambda 作为键传递给元组列表。

```py
# Python code to sort list of tuple based on sum of element in tuple.

# Input list initialisation
Input = [(4, 5), (2, 3), (6, 7), (2, 8)] 

print("The original list of tuple is ")
print(Input)

# Passing lambda as key to sort list of tuple
print("\nThe answer is")
print(sorted(Input, key = lambda x:x[0] + x[1]))
```

**输出:**

```py
The original list of tuple is 
[(4, 5), (2, 3), (6, 7), (2, 8)]

The answer is
[(2, 3), (4, 5), (2, 8), (6, 7)]

```

**#方法 3:** 使用[排序()方法](https://www.geeksforgeeks.org/sort-in-python/)
通过该方法排序时，元组的实际内容会发生变化，就像冒泡排序一样，会执行排序的就地方法。

```py
# Python code to sort list of tuple based on sum of element in tuple.

# Input list initialisation
Input = [(4, 5), (2, 3), (6, 7), (2, 8)] 

print("The original list of tuple is ")
print(Input)

# Passing lambda as key to sort list of tuple
Input.sort(key = lambda x: x[0] + x[1])

# Printing output
print("\nThe answer is")
print(Input)
```

**输出:**

```py
The original list of tuple is 
[(4, 5), (2, 3), (6, 7), (2, 8)]

The answer is
[(2, 3), (4, 5), (2, 8), (6, 7)]

```
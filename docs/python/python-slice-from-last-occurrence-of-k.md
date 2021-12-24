# Python–K 最后一次出现的切片

> 原文:[https://www . geeksforgeeks . org/python-从 k 的最后一次出现开始切片/](https://www.geeksforgeeks.org/python-slice-from-last-occurrence-of-k/)

有时，在使用 Python Strings 时，我们可能会遇到一个问题，即我们需要在元素的最后一次出现时执行字符剥离任务。这可能有涉及数据的应用程序。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+字符串切片**
以上方法的结合可以解决这个问题。在这种情况下，我们使用循环搜索最后一次出现，并将索引保存到后面的切片中。

```py
# Python3 code to demonstrate working of 
# Slice from Last Occurrence of K
# Using string slicing and loop

# initializing string
test_str = 'geeksforgeeks-is-best-for-geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = "-"

# Slice from Last Occurrence of K
# Using string slicing and loop
idx = None
for i in range(len(test_str)):
    if K == test_str[i]:
        idx = i
res = test_str[:idx]

# printing result 
print("Sliced String is : " + str(res)) 
```

**Output :**

```py
The original string is : geeksforgeeks-is-best-for-geeks
Sliced String is : geeksforgeeks-is-best-for

```
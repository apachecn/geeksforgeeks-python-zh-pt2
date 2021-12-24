# Python–最大刺痛整数列表

> 原文:[https://www . geesforgeks . org/python-最大刺痛整数列表/](https://www.geeksforgeeks.org/python-maximum-of-sting-integer-list/)

有时，在处理数据时，我们会遇到一个问题，即我们收到一系列字符串格式的数据列表，我们希望找到每个字符串列表整数的最大值。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `int()`**
这是执行这个任务的蛮力方法。在这种情况下，我们对整个列表运行一个循环，将每个字符串转换为整数，执行 listwise 最大化，并存储在一个单独的列表中。

```
# Python3 code to demonstrate working of
# Maximum of Sting Integer
# using loop + int()

# initialize list 
test_list = [['1', '4'], ['5', '6'], ['7', '10']]

# printing original list 
print("The original list : " + str(test_list))

# Maximum of Sting Integer
# using loop + int()
res = []
for sub in test_list:
    par_max = 0
    for ele in sub:
        par_max = max(par_max, int(ele))
    res.append(par_max)

# printing result
print("List after maximization of nested string lists : " + str(res))
```

**Output :**

```
The original list : [['1', '4'], ['5', '6'], ['7', '10']]
List after maximization of nested string lists : [4, 6, 10]

```
# Python–奇数元素索引

> 原文:[https://www.geeksforgeeks.org/python-odd-elements-indices/](https://www.geeksforgeeks.org/python-odd-elements-indices/)

有时，在使用 Python 列表时，我们可能会遇到希望找到奇数元素的问题。这项工作可以在许多领域进行，例如网页开发和使用数据库。我们有时可能需要找到它们的索引。让我们讨论寻找奇数元素索引的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。在这种情况下，我们检查列表中的奇数元素，并相应地附加其索引。

```
# Python3 code to demonstrate working of 
# Odd elements indices
# using loop 

# initialize list 
test_list = [5, 6, 10, 4, 7, 1, 19] 

# printing original list 
print("The original list is : " + str(test_list)) 

# Odd elements indices
# using loop 
res = [] 
for idx, ele in enumerate(test_list): 
    if ele % 2 != 0: 
        res.append(idx) 

# printing result 
print("Indices list Odd elements is : " + str(res)) 
```

**Output :**

```
The original list is : [5, 6, 10, 4, 7, 1, 19]
Indices list Odd elements is : [0, 4, 5, 6]

```
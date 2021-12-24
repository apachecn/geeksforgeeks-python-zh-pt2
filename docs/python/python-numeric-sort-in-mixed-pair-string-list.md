# Python–混合对字符串列表中的数字排序

> 原文:[https://www . geesforgeks . org/python-数值-混合对排序-字符串-列表/](https://www.geeksforgeeks.org/python-numeric-sort-in-mixed-pair-string-list/)

有时，在处理数据记录时，我们可能会遇到一个问题，即我们以自定义格式接收数据，并且我们需要执行排序。我们可以接收人名和空格分隔的分数，并要求得到最佳到最差的排序。让我们讨论一下解决这个特殊问题的方法。

**方法#1:使用`split() + sort()` +按键功能**
上述功能的组合可用于执行该任务。在这种情况下，我们使用外部函数执行排序，其中我们分割字符串并提取数字部分。

```
# Python3 code to demonstrate 
# Numeric Sort in Mixed Pair String List
# using split() + sort() + key function

# helper function 
def helper_func(ele):
        name, val = ele.split()
        return int(val)

# Initializing list
test_list = ["Manjeet 5", "Akshat 7", "Akash 6", "Nikhil 10"]

# printing original list
print("The original list is : " + str(test_list))

# Numeric Sort in Mixed Pair String List
# using split() + sort() + key function
test_list.sort(key = helper_func, reverse = True)

# printing result 
print ("The reverse sorted numerics are : " + str(test_list))
```

**Output :**

```
The original list is : ['Manjeet 5', 'Akshat 7', 'Akash 6', 'Nikhil 10']
The reverse sorted numerics are : ['Nikhil 10', 'Akshat 7', 'Akash 6', 'Manjeet 5']

```
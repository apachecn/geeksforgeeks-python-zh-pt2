# Python–将所有重复出现的内容替换为 N

> 原文:[https://www . geeksforgeeks . org/python-将所有重复出现替换为-n/](https://www.geeksforgeeks.org/python-replace-all-repeated-occurrences-with-n/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，需要用另一个元素替换一个元素。但是人们可以有这些变化，如增加数量和保持第一次出现。这可以在各种领域得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`enumerate() + set()` +循环**
上述功能的组合可用于执行该任务。在这种情况下，我们迭代列表，然后将第一个出现的值存储在集合中，使用 In 测试连续的值，并在原地替换。

```
# Python3 code to demonstrate 
# Replace all repeated occurrences of K with N
# using enumerate() + set() + loop

# Initializing list
test_list = [1, 3, 3, 1, 4, 4, 1, 5, 5]

# printing original list
print("The original list is : " + str(test_list))

# Initializing N 
N = 'rep'

# Replace all repeated occurrences of K with N
# using enumerate() + set() + loop
his = set([])
for idx, ele in enumerate(test_list):
    if ele in his:
        test_list[idx] = N
    his.add(ele)

# printing result 
print ("The duplication altered list : " + str(test_list))
```

**Output :**

```
The original list is : [1, 3, 3, 1, 4, 4, 1, 5, 5]
The duplication altered list : [1, 3, 'rep', 'rep', 4, 'rep', 'rep', 5, 'rep']

```
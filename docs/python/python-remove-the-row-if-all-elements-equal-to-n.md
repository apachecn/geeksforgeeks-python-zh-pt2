# Python–如果所有元素都等于 N，则删除该行

> 原文:[https://www . geesforgeks . org/python-如果所有元素都等于 n，则移除行/](https://www.geeksforgeeks.org/python-remove-the-row-if-all-elements-equal-to-n/)

有时，在处理数据时，尤其是在机器学习领域，我们需要经历大量相似的 N 个相等的数据。我们有时需要删除所有等于 N 的行。让我们讨论某些方法来删除所有 N 值都作为列表列的行。

**方法#1:使用列表理解+ `count() + len()`**
我们可以使用列表理解食谱来执行这个特定的任务，与 len 和 count 函数的组合合作来检查与列表长度相等的相似性元素计数器。

```py
# Python3 code to demonstrate
# N row deletion in Matrix
# using list comprehension + count() + len()

# initializing matrix
test_list = [[1, 4, 2], [False, 9, 3],
            [6, 6, 6], [1, 0, 1]]

# printing original list
print("The original list : " + str(test_list))

# initializing N 
N = 6

# using list comprehension + count() + len()
# N row deletion in Matrix
res = [sub for sub in test_list if sub.count(N) != len(sub)]

# print result
print("The list after removal of N rows : " + str(res))
```

**Output :**

```py
The original list : [[1, 4, 2], [False, 9, 3], [6, 6, 6], [1, 0, 1]]
The list after removal of N rows : [[1, 4, 2], [False, 9, 3], [1, 0, 1]]

```
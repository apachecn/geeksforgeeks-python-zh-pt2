# Python–将元素配对到字典中

> 原文:[https://www . geesforgeks . org/python-pair-list-elements-to-dictionary/](https://www.geeksforgeeks.org/python-pair-lists-elements-to-dictionary/)

有时，在处理记录时，我们可能会遇到这样的问题，即我们可能有成对的列表，我们需要将类似的元素配对到单键值字典。这是一个非常特殊的问题，但是可以在数据领域中得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `extend() + enumerate()`**
上述功能的组合可以用来解决这个问题。在本文中，我们对列表进行迭代，并使用 extend()将相似的元素追加到相似的键中。

```py
# Python3 code to demonstrate working of 
# Pair lists elements to Dictionary
# Using loop + extend() + enumerate()

# initializing lists
test_list1 = [1, 2, 3, 1, 1, 2, 3]
test_list2 = [[4, 5], [6, 7], [2, 3], [10, 12], 
                 [56, 43], [98, 100], [0, 13]]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Pair lists elements to Dictionary
# Using loop + extend() + enumerate()
res = dict()
for idx, val in enumerate(test_list1):
    if val in res:
        res[val].extend(list(test_list2[idx]))
    else:
        res[val] = list(test_list2[idx])

# printing result 
print("The Like elements compiled Dictionary is : " + str(res)) 
```

**Output :**

> 原列表 1 为:[1，2，3，1，1，2，3]
> 原列表 2 为:[[4，5]，[6，7]，[2，3]，[10，12]，[56，43]，[98，100]，[0，13]]
> 已编译的 Like 元素字典为:{1: [4，5，10，12，56，43]，2: [6，7，98，100]，3: [2，3，3
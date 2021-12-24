# Python–测试公共元素顺序

> 原文:[https://www . geesforgeks . org/python-test-common-elements-order/](https://www.geeksforgeeks.org/python-test-common-elements-order/)

有时，在处理列表时，我们会遇到一个问题，需要测试列表是否包含公共元素。这种问题已经处理过很多次了，有很多解决方法。但是有时候，我们可能会遇到一个问题，我们需要检查这些公共元素在两个列表中是否以相同的顺序出现。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `set()`**
以上功能的组合可以用来执行这个任务。在这种情况下，我们遍历列表，并使用我们拥有的条件来检查公共元素是否有序。使用 set()执行复制删除。

```py
# Python3 code to demonstrate 
# Test Common Elements Order
# using loop + set()

# helper function
def common_ord(test_list1, test_list2):
    comm = set(test_list1)
    comm.intersection_update(test_list2)
    pr_idx = 0
    for ele in test_list1:
        if ele in comm:
            try:
                pr_idx = test_list2.index(ele, pr_idx)
            except ValueError:
                return False
    return True

# Initializing lists
test_list1 = ['Gfg', 'is', 'for', 'Geeks']
test_list2 = [1, 'Gfg', 2, 'Geeks']

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Test Common Elements Order
# using loop + set()
res = common_ord(test_list1, test_list2)

# printing result 
print ("Are common elements in order ? : " + str(res))
```

**Output :**

```py
The original list 1 is : ['Gfg', 'is', 'for', 'Geeks']
The original list 2 is : [1, 'Gfg', 2, 'Geeks']
Are common elements in order ? : True

```
# Python–重新排列第二个索引大于第一个索引的元素

> 原文:[https://www . geesforgeks . org/python-重排-元素-第二-索引-大于第一/](https://www.geeksforgeeks.org/python-rearrange-elements-second-index-greater-than-first/)

给定两个列表，对于给定的索引，第二个列表元素总是比第一个大，如果不是，我们重新排列它。

> **输入** : test_list1 = [36，38，40，132]，test_list2 = [35，37，39，41，133]
> **输出** : [37，39，41，133]
> **解释**:结果列表中的每个元素都大于第一个列表的索引对应元素。(例 37 > 36)
> 
> **输入** : test_list1 = [2，6]，test_list2 = [5，3，8]
> **输出** : [5，8]
> **解释**:这里 5 > 2 和 8 > 6。

**方法:使用循环**
这是解决这个问题的蛮方法。在这种情况下，我们试图在整个列表遍历之后获得最佳的合适的下一个更高的元素，并执行必要的重排。

```py
# Python3 code to demonstrate working of 
# Rearrange elements second index greater than first
# Using loop

# initializing lists
test_list1 = [14, 16, 18, 110]
test_list2 = [13, 15, 17, 19, 111]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Rearrange elements second index greater than first
# Using loop
x = y = 0
res1, res2 = [], []
while x < len(test_list2) and y < len(test_list1):

    # checking for greater element
    if test_list2[x] > test_list1[y]:
        res2.append(test_list2[x])
        res1.append(test_list1[y])
        while y < len(test_list1) and test_list2[x] > test_list1[y]:
            res1[-1] = test_list1[y]
            y += 1
    x += 1

# printing result 
print("List 2 after conversion : " + str(res2))
```

**Output :**

```py
The original list 1 is : [14, 16, 18, 110]
The original list 2 is : [13, 15, 17, 19, 111]
List 2 after conversion : [15, 17, 19, 111]

```
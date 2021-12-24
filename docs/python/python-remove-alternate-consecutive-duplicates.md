# Python–删除交替的连续副本

> 原文:[https://www . geesforgeks . org/python-remove-alternate-continuous-duplicates/](https://www.geeksforgeeks.org/python-remove-alternate-consecutive-duplicates/)

给定元素列表，移除元素的交替连续副本。

> **输入**:test _ list =【5，5，5，5，6，6】
> **输出**:【5，5，6】
> **解释**:候补 occ。5 和 6 的值被删除。
> 
> **输入**:test _ list =【5，5，5，5】
> **输出**:【5，5】
> **解释**:候补 occ。其中 5 个被移除。

**方法:使用 loop + remove()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们迭代每个元素，并使用额外的先前元素变量来跟踪替代标准。使用移除()执行移除。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove alternate consecutive duplicates
# Using loop + remove()

# initializing lists
test_list = [5, 5, 5, 5, 6, 6, 8, 3, 3, 8]

# printing original list
print("The original list : " + str(test_list))

# Using loop to iterate through elements
# element to keep track
temp = test_list[0]
count = 0
org_list = test_list
idx = 0
while(1):

    # break when idx greater than size
    if idx >= len(org_list):
        break

    # check for alternates 
    if count % 2 and temp == test_list[idx]:
        test_list.remove(test_list[idx])
        idx = idx - 1
        count += 1
        temp = test_list[idx]
    else:

        # keeping track of alternate index increment
        # and assignment
        if temp != test_list[idx]:
            count = 1
            temp = test_list[idx]
        else :
            count += 1
    idx = idx + 1

# printing result 
print("List after alternate duplicates removal : " + str(test_list))
```

**Output**

```py
The original list : [5, 5, 5, 5, 6, 6, 8, 3, 3, 8]
List after alternate duplicates removal : [5, 5, 6, 8, 3, 8]

```
# Python–在下一个较大值上拆分列表

> 原文:[https://www . geeksforgeeks . org/python-拆分-下一个列表-较大值/](https://www.geeksforgeeks.org/python-split-list-on-next-larger-value/)

给定一个列表，对下一个较大的值执行拆分。

> **输入** : test_list = [4，2，3，7，5，1，3，4，11，2]
> **输出** : [[4，2，3]，[7，5，1，3，4]，[11，2]]
> **解释**:大于 4，7 后，在该元素发生分裂，以此类推。
> 
> **输入** : test_list = [4，2，3，7，5，1，3，4，1，2]
> **输出** : [[4，2，3]，[7，5，1，3，4，1，2]]
> **解释**:4，7 越大，该元素发生分裂。

**方法:使用循环**

在这种情况下，我们迭代列表并跟踪分割值，如果发现比记录值更高的值，则根据它创建新列表，并且分割值是当前值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Split List on next larger value
# Using loop

# initializing list
test_list = [4, 2, 3, 7, 5, 9, 3, 4, 11, 2]

# printing original list
print("The original list is : " + str(test_list))

# starting value as ref.
curr = test_list[0]
temp = []
res = []
for ele in test_list:

    # if curr value greater than split
    if ele > curr:
        res.append(temp)
        curr = ele
        temp = []
    temp.append(ele)
res.append(temp)

# printing results
print("Split List : " + str(res))
```

**Output**

```py
The original list is : [4, 2, 3, 7, 5, 9, 3, 4, 11, 2]
Split List : [[4, 2, 3], [7, 5], [9, 3, 4], [11, 2]]

```
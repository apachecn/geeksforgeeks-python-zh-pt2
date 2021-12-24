# Python–K 后最小的缺失元素

> 原文:[https://www . geesforgeks . org/python-minist-missing-element-after-k/](https://www.geeksforgeeks.org/python-smallest-missing-element-after-k/)

给定一个列表，得到列表中 K 之后最小的缺失元素。

> **输入** : test_list = [1，3，4，5，7，9，10]，K = 5
> **输出** : 6
> **解释**:5，6 之后是列表中缺少的第 1 个元素。
> 
> **输入** : test_list = [1，3，4，5，7，9，11]，K = 9
> **输出** : 10
> **解释**:9 之后，列表中缺少第 10 个元素。

**进场:使用循环**

在这种情况下，我们遍历数字，并使用条件句检查列表中是否缺少大于 K 的元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Smallest missing element after K
# Using loop

# initializing list
test_list = [1, 3, 4, 5, 7, 9, 10]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 7

ele = 1

# infinite loop to break at element found
while(1):

        # checking if greater than K and not in list
    if ele > K and ele not in test_list:
        res = ele
        break
    ele = ele + 1

# printing result
print("The Smallest element greater than K in list : " + str(res))
```

**Output**

```py
The original list is : [1, 3, 4, 5, 7, 9, 10]
The Smallest element greater than K in list : 8

```
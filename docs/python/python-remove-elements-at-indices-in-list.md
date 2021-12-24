# Python–删除列表中索引处的元素

> 原文:[https://www . geesforgeks . org/python-remove-elements-at-indexes-in-list/](https://www.geeksforgeeks.org/python-remove-elements-at-indices-in-list/)

给定列表，移除索引列表中的所有元素。

> **输入** : test_list = [5，6，3，7，8，1，2，10]，idx_list = [2，4，5]
> **输出**:【5，6，7，2，10】
> **说明**已删除:3，6，1。
> **输入** : test_list = [5，6，3，7，8，1，2，10]，idx_list = [2]
> **输出**:【5，6，7，8，1，2，10】
> **说明** : 3 已删除。

**方法#1:使用 enumerate() +循环**

在这种情况下，我们对所有元素进行迭代，如果列表中存在索引，则结果列表中省略该索引元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove elements at Indices in List
# Using loop

# initializing list
test_list = [5, 6, 3, 7, 8, 1, 2, 10]

# printing original list
print("The original list is : " + str(test_list))

# initializing idx list
idx_list = [2, 4, 5, 7]

res = []
for idx, ele in enumerate(test_list):

    # checking if element not present in index list
    if idx not in idx_list:
        res.append(ele)

# printing results
print("Filtered List after removal : " + str(res))
```

**Output**

```
The original list is : [5, 6, 3, 7, 8, 1, 2, 10]
Filtered List after removal : [5, 6, 7, 2]
```

**方法 2:使用 enumerate() +列表理解**

在这种情况下，我们使用列表理解以紧凑的方式执行迭代任务，其余方法与上面类似。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove elements at Indices in List
# Using enumerate() + list comprehension

# initializing list
test_list = [5, 6, 3, 7, 8, 1, 2, 10]

# printing original list
print("The original list is : " + str(test_list))

# initializing idx list
idx_list = [2, 4, 5, 7]

# one-liner to test for element in index list
res = [ele for idx, ele in enumerate(test_list) if idx not in idx_list]

# printing results
print("Filtered List after removal : " + str(res))
```

**Output**

```
The original list is : [5, 6, 3, 7, 8, 1, 2, 10]
Filtered List after removal : [5, 6, 7, 2]
```
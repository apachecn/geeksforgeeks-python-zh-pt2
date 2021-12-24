# Python 程序删除列表

中 x 之前的每个 y

> 原文:[https://www . geesforgeks . org/python-program-to-remove-event-y-before-x-in-list/](https://www.geeksforgeeks.org/python-program-to-remove-each-y-occurrence-before-x-in-list/)

给定一个列表，移除列表中元素 x 之前所有出现的 y。

> **输入** : test_list = [4，5，7，4，6，7，4，9，1，4]，x，y = 6，4
> **输出** : [5，7，6，7，4，9，1，4]
> **解释**:6 之前 4 的所有出现都被删除。
> 
> **输入** : test_list = [4，5，7，4，6，7，4，9，1，4]，x，y = 6，7
> **输出** : [4，5，4，6，7，4，9，1，4]
> **解释**:6 之前所有出现的 7 都被删除。

**方法#1:使用列表理解+索引()**

在这种情况下，我们使用 index()获得 x 的索引，并在 x 之前检查 y，如果存在，则从结果列表中排除。使用列表比较来执行迭代和比较。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove each y occurrence before x in List
# Using list comprehension + index()

# initializing list
test_list = [4, 5, 7, 4, 6, 7, 4, 9, 1, 4]

# printing original lists
print("The original list is : " + str(test_list))

# initializing x and y 
x, y = 6, 4

# getting index using index()
xidx = test_list.index(x)

# retain all values other than y, and y if its index greater than x index
res = [ele for idx, ele in enumerate(test_list) if ele != y or (ele == y and idx > xidx) ]

# printing result 
print("Filtered List " + str(res))
```

**输出:**

```py
The original list is : [4, 5, 7, 4, 6, 7, 4, 9, 1, 4]
Filtered List [5, 7, 6, 7, 4, 9, 1, 4]

```

**方法 2:使用循环+索引()**

这个过滤任务是使用循环中的比较运算符来完成的，index()用于获取列表中 x 的索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove each y occurrence before x in List
# Using loop + index()

# initializing list
test_list = [4, 5, 7, 4, 6, 7, 4, 9, 1, 4]

# printing original lists
print("The original list is : " + str(test_list))

# initializing x and y 
x, y = 6, 4

# getting index using index()
xidx = test_list.index(x)

# filtering using comparison operators
res = []
for idx, ele in enumerate(test_list):
  if ele != y or (ele == y and idx > xidx):
    res.append(ele)

# printing result 
print("Filtered List " + str(res))
```

**输出:**

```py
The original list is : [4, 5, 7, 4, 6, 7, 4, 9, 1, 4]
Filtered List [5, 7, 6, 7, 4, 9, 1, 4]

```
# Python 程序删除矩阵中有重复元素的行

> 原文:[https://www . geesforgeks . org/python-程序-删除矩阵中有重复元素的行/](https://www.geeksforgeeks.org/python-program-to-remove-rows-with-duplicate-element-in-matrix/)

给定矩阵，删除其中有重复元素的所有行。

> **输入** : test_list = [[4，3，2]，[7，6，7]，[2，4，4]，[8，9，9]]
> **输出** : [[4，3，2]]
> **解释** : [4，3，2]是唯一唯一的一行。
> 
> **输入** : test_list = [[4，3，3，2]，[7，6，7]，[2，4，4]，[8，9，9]]
> **输出** : []
> **解释**:无唯一行。

**方法一:使用列表理解+ set() + len()**

在这种情况下，我们只提取在将其转换为[集合](https://www.geeksforgeeks.org/sets-in-python/)后保持相同长度的行。

## 蟒蛇 3

```py
# initializing list
test_list = [[4, 3, 2], [7, 6, 7], [2, 4, 5], [8, 9, 9]]

# printing original list
print("The original list is : " + str(test_list))

# set() removing all elements
# list comprehension used to filter
res = [sub for sub in test_list if len(set(sub)) == len(sub)]

# printing result
print("Rows after removal : " + str(res))
```

**Output**

```py
The original list is : [[4, 3, 2], [7, 6, 7], [2, 4, 5], [8, 9, 9]]
Rows after removal : [[4, 3, 2], [2, 4, 5]]

```

**方法 2:使用滤镜()+λ+set()+len()**

在本例中，我们使用 [filter()](https://www.geeksforgeeks.org/filter-in-python/) + [lambda 函数](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)执行过滤任务，并使用 set 和 len()进行检查。

## 蟒蛇 3

```py
# initializing list
test_list = [[4, 3, 2], [7, 6, 7], [2, 4, 5], [8, 9, 9]]

# printing original list
print("The original list is : " + str(test_list))

# set() removing all elements
# filter() used to filter
res = list(filter(lambda ele: len(set(ele)) == len(ele), test_list))

# printing result
print("Rows after removal : " + str(res))
```

**Output**

```py
The original list is : [[4, 3, 2], [7, 6, 7], [2, 4, 5], [8, 9, 9]]
Rows after removal : [[4, 3, 2], [2, 4, 5]]

```
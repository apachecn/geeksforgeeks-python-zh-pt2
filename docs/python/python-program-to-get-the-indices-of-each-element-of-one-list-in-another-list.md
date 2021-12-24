# Python 程序获取一个列表的每个元素在另一个列表中的索引

> 原文:[https://www . geeksforgeeks . org/python-program-to-get-indexes-of-in-list-in-list-other-list/](https://www.geeksforgeeks.org/python-program-to-get-the-indices-of-each-element-of-one-list-in-another-list/)

给定两个列表，从列表 1 中获取列表 2 中每个元素所有出现的所有索引。

> **输入** : test_list = [4，5，3，7，8，3，2，4，3，5，8，3]，get_list = [7，5，4]
> **输出** : [[3]，[1，9]，[0，7]]
> **解释**:第 1 和第 9 个索引出现 5。
> 
> **输入** : test_list = [4，5，3，7，8，3，2，4，3，5，8，3]，get_list = [7，5，8]
> **输出** : [[3]，[1，9]，[4，10]]
> **说明**:第 4、第 10 个指标出现 8。

**方法#1:使用循环+ setdefault()**

在这种情况下，我们执行的任务是将所有元素列表按其索引分组，在第二次运行中，只获取其他列表中存在的元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Multiple Indices from list elements
# Using setdefault() + loop

# initializing list
test_list = [4, 5, 3, 7, 8, 3, 2, 4, 3, 5, 8, 3]

# printing original list
print("The original list is : " + str(test_list))

# initializing get_list 
get_list = [7, 5, 3]

# getting all elements indices
ele_indices = dict()  
for idx, val in enumerate(test_list):
    ele_indices.setdefault(val, []).append(idx)

# filtering only required elements
res = [ele_indices.get(idx, [None]) for idx in get_list]   

# printing result 
print("Filtered Indices of elements in list 1  : " + str(res))
```

**Output**

```
The original list is : [4, 5, 3, 7, 8, 3, 2, 4, 3, 5, 8, 3]
Filtered Indices of elements in list 1  : [[3], [1, 9], [2, 5, 8, 11]]

```

**方法 2:使用列表理解+枚举()**

在这种情况下，我们使用嵌套循环来获取所有索引，然后在另一个列表中出现的情况下进行过滤。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Multiple Indices from list elements
# Using list comprehension + enumerate()

# initializing list
test_list = [4, 5, 3, 7, 8, 3, 2, 4, 3, 5, 8, 3]

# printing original list
print("The original list is : " + str(test_list))

# initializing get_list 
get_list = [7, 5, 3]

# enumerate() used to get idx, val simultaneously
res = [([idx for idx, val in enumerate(test_list) if val == sub] if sub in test_list else [None])
      for sub in get_list]

# printing result 
print("Indices of elements in list 1  : " + str(res))
```

**Output**

```
The original list is : [4, 5, 3, 7, 8, 3, 2, 4, 3, 5, 8, 3]
Indices of elements in list 1  : [[3], [1, 9], [2, 5, 8, 11]]

```
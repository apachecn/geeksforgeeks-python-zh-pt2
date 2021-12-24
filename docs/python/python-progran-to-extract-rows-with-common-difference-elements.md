# Python 程序提取具有共同差异元素的行

> 原文:[https://www . geeksforgeeks . org/python-progran-提取具有公共差异元素的行/](https://www.geeksforgeeks.org/python-progran-to-extract-rows-with-common-difference-elements/)

给定一个矩阵，用 AP 序列提取行。

> **输入** : test_list = [[4，7，10]，[8，10，12]，[10，11，13]，[6，8，10]]
> **输出** : [[4，7，10]，[8，10，12]，[6，8，10]]
> **解释** : 3，4，2 是 AP 中常见的区别。
> 
> **输入** : test_list = [[4，7，10]，[8，10，13]，[10，11，13]，[6，8，10]]
> **输出** : [[4，7，10]，[6，8，10]]
> **说明** : 3 和 2 是 AP 中常见的区别。

**方法#1:使用循环**

在这种情况下，我们使用一个循环来检查所有具有共同差异的元素，如果发现任何元素不同步，则该行被标记为关闭，不添加到结果中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract rows with common difference elements
# Using loop

# initializing list
test_list = [[4, 7, 10],
             [8, 10, 12],
             [10, 11, 13],
             [6, 8, 10]]

# printing original list
print("The original list is : " + str(test_list))

res = []
for row in test_list:
    flag = True
    for idx in range(0, len(row) - 1):

        # check for common difference
        if row[idx + 1] - row[idx] != row[1] - row[0]:
            flag = False
            break
    if flag :
        res.append(row)

# printing result
print("Filtered Matrix : " + str(res))
```

**输出:**

> 原列表为:[[4，7，10]，[8，10，12]，[10，11，13]，[6，8，10]]
> 过滤矩阵:[[4，7，10]，[8，10，12]，[6，8，10]]

**方法 2:使用 all() +列表理解**

在这种情况下，我们使用 all()检查所有值是否有共同的差异，列表理解用于执行行的迭代。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# all() + list comprehension
# Using list comprehension + all()

# initializing list
test_list = [[4, 7, 10],
             [8, 10, 12],
             [10, 11, 13],
             [6, 8, 10]]

# printing original list
print("The original list is : " + str(test_list))

# checking for all values to have common difference        
res = [row for row in test_list
       if all(row[idx + 1] - row[idx] == row[1] - row[0]
              for idx in range(0, len(row) - 1))]

# printing result
print("Filtered Matrix : " + str(res))
```

**输出:**

> 原列表为:[[4，7，10]，[8，10，12]，[10，11，13]，[6，8，10]]
> 过滤矩阵:[[4，7，10]，[8，10，12]，[6，8，10]]
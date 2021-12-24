# 获取字符串构造最小元素的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-get-minimum-elements-for-string-construction/](https://www.geeksforgeeks.org/python-program-to-get-minimum-elements-for-string-construction/)

给定一个字符串，任务是编写一个 Python 程序来计算从列表元素形成字符串所需的最少元素。

> **输入**:test _ list =[“geek”、“ring”、“staff”、“ok”、“wake”]，tar _ str =“work”
> **输出** : 2
> **说明**:work 可以使用 wake 和 ring 形成。
> 
> **输入**:test _ list =[“geek”、“ring”、“staff”、“ok”、“wake”]，tar _ str =“work ingeek”
> **输出** : 3
> **解释**:work ingeek 可以使用 wake、geek 和 ring 来形成。

**方法:**使用[issubset()](https://www.geeksforgeeks.org/issubset-in-python/)+[set()](https://www.geeksforgeeks.org/python-set-method/)+组合()

在这种情况下，我们迭代字符串列表并形成所有大小的组合，每个组合都被转换为 set，并使用 issubset()检查是否形成目标字符串，如果找到，则退出循环并记录计数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Minimum elements for String construction
# Using issubset() + set() + combinations()
from itertools import combinations

# initializing list
test_list = ["geek", "ring", "sfor", "ok", "woke"]

# printing original list
print("The original list is : " + str(test_list))

# initializing target string 
tar_str = "working"

res = -1
set_str = set(tar_str)
done = False
for val in range(0, len(test_list) + 1):

    # creating combinations
    for sub in combinations(test_list, val):

        # contructing sets of each combinations 
        temp_set = set(ele for subl in sub for ele in subl)

        # checking if target string has created set as subset
        if set_str.issubset(temp_set):
            res = val
            done = True
            break
    if done:
        break

# printing result 
print("The Minimum count elements for string : " + str(res))
```

**输出:**

```
The original list is : ['geek', 'ring', 'sfor', 'ok', 'woke']
The Minimum count elements for string : 2
```
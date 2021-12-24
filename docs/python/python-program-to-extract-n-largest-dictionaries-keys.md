# Python 程序提取 N 个最大字典键

> 原文:[https://www . geesforgeks . org/python-程序-提取-n-最大-字典-键/](https://www.geeksforgeeks.org/python-program-to-extract-n-largest-dictionaries-keys/)

给定一个字典，按降序提取 N 个最大的字典键。

> **输入** : test_dict = {6 : 2，8: 9，3: 9，10: 8}，N = 3
> **输出**:【10，8，6】
> **解释**:最大。按降序提取的 n 个键。
> 
> **输入** : test_dict = {6 : 2，8: 9，3: 9，10: 8}，N = 2
> **输出**:【10，8】
> **解释** : Max。按降序提取的 n 个键。

**方法#1:使用排序()+λ+反转**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 sorted() + lambda 执行关键字排序，使用 reverse 执行反向排序以获得所需的排序。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract top N Dictionaries by Key
# Using sorted() + lambda + reverse

# initializing dictionary
test_dict = {6 : 2, 8: 9, 3: 9, 10: 8}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing N 
N = 4

res = []

# 0 in lambda used for keys, list sliced till N for top N values
for key, val in sorted(test_dict.items(), key = lambda x: x[0], reverse = True)[:N]:
    res.append(key)

# printing result 
print("Top N keys are: " + str(res))
```

**Output**

```
The original dictionary is : {6: 1, 8: 9, 3: 9, 10: 8}
Top N keys are: [10, 8, 6, 3]

```

**方法 2:使用 nlargetst()+lambda**

这是执行这项任务的另一种方式。在这种情况下，最大值使用 nlargest()提取，lambda 函数用于驱动密钥提取和比较逻辑。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract top N Dictionaries by Key
# Using nlargest() + lambda
from heapq import nlargest

# initializing dictionary
test_dict = {6 : 2, 8: 9, 3: 9, 6: 1, 10: 8}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing N 
N = 4

res = []

# Using nlargest() to get maximum keys 
for key, val in nlargest(N, test_dict.items(), key = lambda ele: ele[0]):
    res.append(key)

# printing result 
print("Top N keys are: " + str(res))
```

**Output**

```
The original dictionary is : {6: 1, 8: 9, 3: 9, 10: 8}
Top N keys are: [10, 8, 6, 3]

```
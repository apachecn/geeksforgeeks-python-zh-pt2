# Python–最大长度为 K 的字符串

> 原文:[https://www . geesforgeks . org/python-最大长度为 k 的字符串/](https://www.geeksforgeeks.org/python-strings-with-maximum-k-length/)

有时，在处理大量数据时，我们可能会遇到一个问题，即我们需要提取不超过特定长度的特定大小的字符串。这种问题可能会在跨多个领域的验证案例中出现。让我们在 Python 字符串列表中讨论处理这个问题的特定方法。
**方法#1:使用列表理解+ len()**
上述功能的组合可用于执行此任务。在这种情况下，我们迭代所有字符串，只返回长度小于使用 len()检查的 K 的字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract Strings with Maximum K length
# using list comprehension + len()

# initialize list
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list : " + str(test_list))

# initialize K
K = 3

# Extract Strings with Maximum K length
# using list comprehension + len()
res = [ele for ele in test_list if len(ele) <= K]

# printing result
print("The maximum K sized strings are : " + str(res))
```

**Output : **

```
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
The maximum K sized strings are : ['gfg', 'is', 'for']
```

**方法 2:使用 filter() + lambda**
上述功能的组合可用于执行此任务。在本例中，我们使用 filter()提取元素，逻辑在 lambda 函数中编译。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract Strings with Maximum K length
# using filter() + lambda

# initialize list
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list : " + str(test_list))

# initialize K
K = 3

# Extract Strings with Maximum K length
# using filter() + lambda
res = list(filter(lambda ele: len(ele) <= K, test_list))

# printing result
print("The maximum K sized strings are : " + str(res))
```

**Output : **

```
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
The maximum K sized strings are : ['gfg', 'is', 'for']
```
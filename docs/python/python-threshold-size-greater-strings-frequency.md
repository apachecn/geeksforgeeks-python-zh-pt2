# Python |阈值大小更大的字符串频率

> 原文:[https://www . geesforgeks . org/python-threshold-size-greater-strings-frequency/](https://www.geeksforgeeks.org/python-threshold-size-greater-strings-frequency/)

有时，在处理大量数据时，我们会遇到一个问题，即我们需要知道大于特定长度的特定大小字符串的数量。这种问题可能会在跨多个领域的验证案例中出现。让我们在 Python 字符串列表中讨论处理这个问题的特定方法。

**方法#1:使用列表理解+ len()**
上述功能的组合可用于执行此任务。在这种情况下，我们迭代所有字符串，只返回长度大于 K 的字符串，使用 len()进行检查。使用 len()提取计数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Threshold Size Greater Strings Frequency
# using list comprehension + len()

# initialize list
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list : " + str(test_list))

# initialize K
K = 3

# Threshold Size Greater Strings Frequency
# using list comprehension + len()
res = len([ele for ele in test_list if len(ele) >= K])

# printing result
print("The frequency of threshold K sized strings are : " + str(res))
```

**Output**

```py
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
The frequency of threshold K sized strings are : 4
```

**方法 2:使用 filter() + len() + lambda**
上述功能的组合可用于执行此任务。在本例中，我们使用 filter()提取元素，逻辑在 lambda 函数中编译。使用 len()提取计数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Threshold Size Greater Strings Frequency
# using filter() + lambda + len()

# initialize list
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list : " + str(test_list))

# initialize K
K = 3

# Threshold Size Greater Strings Frequency
# using filter() + lambda + len()
res = len(list(filter(lambda ele: len(ele) >= K, test_list)))

# printing result
print("The frequency of threshold K sized strings are : " + str(res))
```

**Output**

```py
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
The frequency of threshold K sized strings are : 4
```
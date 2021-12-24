# Python–元组中的最大频率

> 原文:[https://www . geesforgeks . org/python-最大元组频率/](https://www.geeksforgeeks.org/python-maximum-frequency-in-tuple/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要找到元组中的最大频率元素。Tuple 是一种非常流行的容器，这种类型的问题在 web 开发领域很常见。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = (6，7，10，11，10)
> 输出 : 10
> 
> **输入** : test_tuple = (5，5，5)
> 输出 : 5

**方法一:使用`count()` +循环**
以上功能的组合可以解决这个问题。这是解决这个问题的蛮力方法。在本文中，我们使用 count()来执行元素计数。

```
# Python3 code to demonstrate working of 
# Maximum frequency in Tuple
# Using loop + count()

# initializing tuple
test_tuple = (6, 7, 8, 6, 7, 10)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Maximum frequency in Tuple
# Using loop + count()
cnt = 0
res = test_tuple[0] 
for ele in test_tuple: 
    curr_freq = test_tuple.count(ele) 
    if(curr_freq> cnt): 
        cnt = curr_freq 
        res = ele 

# printing result 
print("Maximum element frequency tuple : " + str(res))
```

**Output :**

```
The original tuple : (6, 7, 8, 6, 7, 10)
Maximum element frequency tuple : 6

```

**方法 2:使用`max() + Counter()`+λ**
以上功能的组合可以解决这个问题。在本文中，我们使用 Counter()来查找所有元素的频率，使用 max()来查找它的最大值。

```
# Python3 code to demonstrate working of 
# Maximum frequency in Tuple
# Using max() + Counter() + lambda
from collections import Counter

# initializing tuple
test_tuple = (6, 7, 8, 6, 7, 10)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Maximum frequency in Tuple
# Using max() + Counter() + lambda
res = max(Counter(test_tuple).items(), key = lambda ele : ele[1])

# printing result 
print("Maximum element frequency tuple : " + str(res[0]))
```

**Output :**

```
The original tuple : (6, 7, 8, 6, 7, 10)
Maximum element frequency tuple : 6

```
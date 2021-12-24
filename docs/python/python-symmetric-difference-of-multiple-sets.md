# Python–多组对称差

> 原文:[https://www . geesforgeks . org/python-对称多集差/](https://www.geeksforgeeks.org/python-symmetric-difference-of-multiple-sets/)

集合组之间的对称差是属于任何一个集合但不存在于任何其他集合中的元素。给定一个集合列表，任务是编写一个 Python 程序来获得它们的对称差。

> **输入:** test_list = [{5，3，2，6，1}，{7，5，3，8，2}，{9，3}，{0，3，6，7}]
> 
> **输出:** {8，1，9，0}
> 
> **解释:** 8、1、9、0 在整个容器上仅出现 1 次。
> 
> **输入:** test_list = [{5，3，2，6，1}，{7，5，3，8，2}，{9，3}]
> 
> **输出:** {8，1，9}
> 
> **解释:** 8、1、9 在整个容器上仅出现 1 次。

**方法#1:使用** [**计数器()**](https://www.geeksforgeeks.org/counters-in-python-set-1/) **+** [**链. from_iterable()**](https://www.geeksforgeeks.org/python-itertools-chain-from_iterable/)

此方法用于通过展平检查所有频率整体设置为 1 的元素。Counter()提取频率，然后可以提取计数为 1 的所有元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Symmetric Difference of Multiple sets
# Using Counter() + chain.from_iterable() 
from collections import Counter
from itertools import chain

# initializing list
test_list = [{5, 3, 2, 6, 1},
             {7, 5, 3, 8, 2}, 
             {9, 3},
             {0, 3, 6, 7}]

# printing original list
print("The original list is : " + str(test_list))

# getting frequencies using Counter()
# from_iterable() flattens the list 
freq = Counter(chain.from_iterable(test_list))

# getting frequency count 1 
res = {idx for idx in freq if freq[idx] == 1}

# printing result
print("Symmetric difference of multiple list : " + str(res))
```

**输出:**

> 原始列表为:[{1，2，3，5，6}，{2，3，5，7，8}，{9，3}，{0，3，6，7}]
> 
> 多个列表的对称差异:{8，1，9，0}

**方法 2:使用 Counter()+chain . from _ iterable()+**[**物品()**](https://www.geeksforgeeks.org/python-dictionary-items-method/)

与上述方法类似，唯一的区别是它是通过使用 items()提取键和值一步完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Symmetric Difference of Multiple sets
# Using Counter() + chain.from_iterable() + items()
from collections import Counter
from itertools import chain

# initializing list
test_list = [{5, 3, 2, 6, 1},
             {7, 5, 3, 8, 2}, 
             {9, 3}, {0, 3, 6, 7}]

# printing original list
print("The original list is : " + str(test_list))

# clubbing operations using items() to get items 
res = {key for key, val in Counter(chain.
                                   from_iterable(test_list)).
       items() if val == 1}

# printing result
print("Symmetric difference of multiple list : " + str(res))
```

**输出:**

> 原始列表为:[{1，2，3，5，6}，{2，3，5，7，8}，{9，3}，{0，3，6，7}]
> 
> 多个列表的对称差异:{8，1，9，0}
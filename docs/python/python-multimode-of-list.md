# Python–列表多模式

> 原文:[https://www.geeksforgeeks.org/python-multimode-of-list/](https://www.geeksforgeeks.org/python-multimode-of-list/)

有时候，在使用 Python 列表时，我们会遇到一个问题，我们需要在列表中找到模式，即最常出现的字符。但是有时候，我们可以有 1 种以上的模式。这种情况称为多模式。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop +公式**
处理这个问题的更简单的方式是使用公式来寻找多模，并使用 loop shorthands 执行。这是解决这个问题最基本的方法。

```
# Python3 code to demonstrate working of 
# Multimode of List
# using loop + formula 
import math
from collections import Counter

# initialize list 
test_list = [1, 2, 1, 2, 3, 4, 3] 

# printing original list 
print("The original list is : " + str(test_list)) 

# Multimode of List
# using loop + formula 
res = []
test_list1 = Counter(test_list) 
temp = test_list1.most_common(1)[0][1] 
for ele in test_list:
  if test_list.count(ele) == temp:
    res.append(ele)
res = list(set(res))

# printing result 
print("The multimode of list is : " + str(res)) 
```

**Output :**

```
The original list is : [1, 2, 1, 2, 3, 4, 3]
The multimode of list is : [1, 2, 3]

```
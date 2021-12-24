# Python |矩阵真求和

> 原文:[https://www.geeksforgeeks.org/python-matrix-true-summation/](https://www.geeksforgeeks.org/python-matrix-true-summation/)

按条件检查数字/元素是一个人面临的常见问题，几乎在每个程序中都要做。有时，我们还需要获得与特定条件匹配的总数，以区分哪些不匹配，以便进一步利用，如在数据科学中。让我们讨论在矩阵中计算真值的某些方法。

**方法#1:使用`sum()` +生成器表达式**
每当生成器表达式返回 true 时，该方法就使用总和加 1 的技巧。当列表耗尽时，返回与条件匹配的数字总数。

```py
# Python 3 code to demonstrate 
# Matrix True Summation
# using sum() + generator expression 
from itertools import chain

# initializing list 
test_list = [[3, False], [False, 6], [False, 9]] 

# printing original list 
print ("The original list is : " + str(test_list)) 

# using sum() + generator expression 
# Matrix True Summation
res = sum(1 for i in chain.from_iterable(test_list) if i == True) 

# printing result 
print ("The number of True elements: " + str(res)) 
```

**Output :**

```py
The original list is : [[3, True], [True, 6], [True, 9]]
The number of True elements: 3

```
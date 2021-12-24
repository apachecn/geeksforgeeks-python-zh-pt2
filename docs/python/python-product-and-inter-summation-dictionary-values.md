# Python–乘积和互加字典值

> 原文:[https://www . geeksforgeeks . org/python-产品和内部求和-字典-值/](https://www.geeksforgeeks.org/python-product-and-inter-summation-dictionary-values/)

有时，在使用 Python 字典时，我们会遇到一个问题，即我们需要执行整个值列表的乘积，并执行每个列表与其他列表的乘积求和。这种应用在网页开发和日常编程中。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'gfg' : [4]，' is' : [3]，' best' : [5]}
> **输出** : 60
> 
> **输入**:test _ dict = { ' gfg ':[0]}
> **输出** : 0

**方法一:使用`zip() + map() + sum()` +循环**
以上功能的组合可以解决这个问题。在本例中，我们使用 sum()执行值的求和，zip()绑定所有的值。map()用于绑定值列表中所有元素的乘法逻辑。所有这些都是使用循环绑定的。

```
# Python3 code to demonstrate working of 
# Product and Inter Summation dictionary values
# Using zip() + map() + sum() + loop 

# helper function
def mul(sub):
  res = 1
  for ele in sub:
     res *= int(ele)
  return res

# initializing dictionary
test_dict = {'gfg' : [4, 5, 6], 'is' : [1, 3, 4], 'best' : [7, 8, 9]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Product and Inter Summation dictionary values
# Using zip() + map() + sum() + loop 
temp = zip(*test_dict.values())
res = sum(map(mul, temp))  

# printing result 
print("The summations of product : " + str(res)) 
```

**Output :**

> 原字典:{'best': [7，8，9]，' is': [1，3，4]，' gfg': [4，5，6]}
> 积的和:364

**方法 2:使用`map() + reduce() + lambda + zip() + sum()` +生成器表达式**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 reduce 和 lambda 执行乘法任务，而生成器表达式执行迭代任务。

```
# Python3 code to demonstrate working of 
# Product and Inter Summation dictionary values
# Using map() + reduce() + lambda + zip() + sum() + generator expression
from functools import reduce

# initializing dictionary
test_dict = {'gfg' : [4, 5, 6], 'is' : [1, 3, 4], 'best' : [7, 8, 9]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Product and Inter Summation dictionary values
# Using map() + reduce() + lambda + zip() + sum() + generator expression
res = sum(map(lambda ele: reduce(lambda x, y: int(x) * int(y), ele),
                                          zip(*test_dict.values())))

# printing result 
print("The summations of product : " + str(res)) 
```

**Output :**

> 原字典:{'best': [7，8，9]，' is': [1，3，4]，' gfg': [4，5，6]}
> 积的和:364
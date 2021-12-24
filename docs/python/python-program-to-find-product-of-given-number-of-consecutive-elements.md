# Python 程序寻找给定数量的连续元素的乘积

> 原文:[https://www . geesforgeks . org/python-program-to-find-product-of-给定数量的连续元素/](https://www.geeksforgeeks.org/python-program-to-find-product-of-given-number-of-consecutive-elements/)

给定一个列表，任务是编写一个 python 程序，用给定数量的元素的连续元素的乘积来构造一个列表。

> **输入:** test_list = [5，6，2，1，7，5，3]，K = 3
> 
> **输出:**【60，12，14，35，105】
> 
> **说明:** 5 * 6 * 2 = 60，6 * 2 * 1 = 12..等等。
> 
> **输入:** test_list = [5，6，2，1，7，5，3]，K = 4
> 
> **输出:**【60，84，70，105】
> 
> **说明** : 5 * 6 * 2 * 1 = 60，6 * 2 * 1 * 7 = 84..等等。

**方法一:** *使用* [*列表切片*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们使用列表切片来执行获取 K 切片的任务，而获取产品的任务是通过外部函数调用来完成的。

**示例:**

## 蟒蛇 3

```
# getting product
def prod(sub):
    res = 1
    for ele in sub:
        res = ele * res
    return res

# initializing lists
test_list = [5, 6, 2, 1, 7, 5, 3]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

res = []
for idx in range(len(test_list) - K + 1):

    # getting product using external function
    res.append(prod(test_list[idx: idx + K]))

# printing result
print("Computed Products : " + str(res))
```

**输出:**

> 原来的名单是:[5，6，2，1，7，5，3]
> 
> 计算乘积:[60，12，14，35，105]

**方法二:** *使用* [*发生器*](https://www.geeksforgeeks.org/generators-in-python/)*[*切片*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)*[*减少()*](https://www.geeksforgeeks.org/reduce-in-python/) *和* [*mul 运算符*](https://www.geeksforgeeks.org/operator-functions-in-python-set-1/)**

**在这种情况下，生成器用于计算和返回中间结果。获取切片乘法的任务是使用内置函数 reduce()和 mul 运算符完成的。**

****示例:****

## **蟒蛇 3**

```
**from functools import reduce
from operator import mul

# generator function

def sliced_prod(sub, K):
    for idx in range(len(sub) - K + 1):

        # slicing and returning intermediate product
        sliced = sub[idx: idx + K]
        yield reduce(mul, sliced)

# generator function

# initializing lists
test_list = [5, 6, 2, 1, 7, 5, 3]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# calling fnc.
res = list(sliced_prod(test_list, K))

# printing result
print("Computed Products : " + str(res))**
```

****输出:****

> **原来的名单是:[5，6，2，1，7，5，3]**
> 
> **计算乘积:[60，12，14，35，105]**
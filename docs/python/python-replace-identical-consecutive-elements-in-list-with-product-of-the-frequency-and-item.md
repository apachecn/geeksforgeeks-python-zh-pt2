# Python–用频率和项目

的乘积替换列表中相同的连续元素

> 原文:[https://www . geesforgeks . org/python-用频率和项目产品替换列表中相同的连续元素/](https://www.geeksforgeeks.org/python-replace-identical-consecutive-elements-in-list-with-product-of-the-frequency-and-item/)

给定一个列表，任务是编写一个 Python 程序，用频率和项目的乘积替换连续元素的分组。

> **输入:** test_list = [3，3，3，3，6，7，5，5，5，8，8，6，6，6，6，6，1，1，1，2，2]
> 
> **输出:**【12，6，7，15，16，30，3，4】
> 
> **解释:** 3 在连续中出现 4 次，因此，3*4 = 12，结果。
> 
> **输入:** test_list = [3，3，3，3，6，7，5，5，5]
> 
> **输出:**【12，6，7，15】
> 
> **解释:** 5 在连续中出现 3 次，因此，5*3 = 15，结果。

**方法一:使用** [**循环。**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，将元素与前一个元素进行比较，以决定组的结束，如果元素不同，则计算到目前为止的乘积，并作为结果调用元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Equal Consecution Product
# Using loop

# initializing list
test_list = [3, 3, 3, 3, 6, 7, 5, 5, 5, 8,
             8, 6, 6, 6, 6, 6, 1, 1, 1, 2, 2]

# printing original list
print("The original list is : " + str(test_list))

res = []
count = 1
for idx in range(1, len(test_list)):

    # checking with prev element
    if test_list[idx - 1] != test_list[idx]:

        # appending product
        res.append((test_list[idx - 1] * count))
        count = 0
    count += 1
res.append((test_list[-1] * count))

# printing result
print("Elements after equal Consecution product : " + str(res))
```

**输出:**

> 原来的名单是:[3，3，3，3，6，7，5，5，5，8，8，6，6，6，6，6，6，1，1，2，2]
> 
> 相等连续乘积后的元素:[12，6，7，15，16，30，3，4]

**方法二:使用**[**group by()**](https://www.geeksforgeeks.org/itertools-groupby-in-python/)**+sum()**

在这种情况下，使用 groupby()形成组，对分组的元素求和得到所需的乘积。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Equal Consecution Product
# Using groupby() + sum()
from itertools import groupby

# initializing list
test_list = [3, 3, 3, 3, 6, 7, 5, 5, 5, 8, 8, 6, 6, 6, 6, 6, 1, 1, 1, 2, 2]

# printing original list
print("The original list is : " + str(test_list))

# creating Consecution groups and summing for required values
res = [sum(group) for k, group in groupby(test_list)]

# printing result
print("Elements after equal Consecution product : " + str(res))
```

**输出:**

> 原来的名单是:[3，3，3，3，6，7，5，5，5，8，8，6，6，6，6，6，6，1，1，2，2]
> 
> 相等连续乘积后的元素:[12，6，7，15，16，30，3，4]
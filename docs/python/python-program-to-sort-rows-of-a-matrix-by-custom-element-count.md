# Python 程序，通过自定义元素计数对矩阵的行进行排序

> 原文:[https://www . geesforgeks . org/python-程序-按自定义元素计数对矩阵行进行排序/](https://www.geeksforgeeks.org/python-program-to-sort-rows-of-a-matrix-by-custom-element-count/)

给定矩阵，下面的程序显示了如何根据指定列表中数字的出现计数对矩阵的行进行排序。

> **输入** : test_list = [[4，5，1，7]，[6，5]，[9，8，2]，[7，1]]，cus_list = [4，5，7]
> **输出** : [[9，8，2]，[6，5]，[7，1]，[4，5，1，7]]
> **解释** : 0 < 1 = 1 < 3 是自定义元素计数的顺序。
> **输入** : test_list = [[4，5，1，7]，[6，5]，[7，1]]，cus_list = [4，5，7]
> **输出** : [[6，5]，[7，1]，[4，5，1，7]]
> **解释** : 1 = 1 < 3 是自定义元素计数的顺序。

**方法 1 :** *使用* [*排序()*](https://www.geeksforgeeks.org/sort-in-python/) *和* [*len()*](https://www.geeksforgeeks.org/python-string-length-len/)

在这种情况下，我们使用 sort()执行就地排序，并检查所有元素，如果自定义列表中存在元素，则增加计数器，len()返回 length 以获取计数。

## 蟒蛇 3

```
# sorting util.
def get_count(sub):
    return len([ele for ele in sub if ele in cus_list])

# initializing list
test_list = [[4, 5, 1, 7], [6, 5], [9, 8, 2], [7, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing custom list
cus_list = [4, 5, 7]

# performing inplace sort
test_list.sort(key=get_count)

# printing result
print("Sorted Matrix : " + str(test_list))
```

**输出:**

> 原来的名单是:[[4，5，1，7]，[6，5]，[9，8，2]，[7，1]]
> 
> 排序矩阵:[[9，8，2]，[6，5]，[7，1]，[4，5，1，7]]

**方法二:** *使用* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)*[*λ*](https://www.geeksforgeeks.org/python-lambda/)*和* [*len()*](https://www.geeksforgeeks.org/python-string-length-len/)*

*解决这个问题的另一种方法是使用 sorted()执行排序任务，lambda 函数提供一个语句逻辑，而不调用外部函数。*

## *蟒蛇 3*

```
*# initializing list
test_list = [[4, 5, 1, 7], [6, 5], [9, 8, 2], [7, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing custom list
cus_list = [4, 5, 7]

# performing sort using sorted()
res = sorted(test_list, key=lambda sub: len(
    [ele for ele in sub if ele in cus_list]))

# printing result
print("Sorted Matrix : " + str(res))*
```

***输出:***

> *原来的名单是:[[4，5，1，7]，[6，5]，[9，8，2]，[7，1]]*
> 
> *排序矩阵:[[9，8，2]，[6，5]，[7，1]，[4，5，1，7]]*
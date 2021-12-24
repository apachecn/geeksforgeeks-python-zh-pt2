# Python–列表中两个元素之间最近的匹配

> 原文:[https://www . geeksforgeeks . org/python-列表中两个元素之间的最近出现次数/](https://www.geeksforgeeks.org/python-nearest-occurrence-between-two-elements-in-a-list/)

给定一个列表和两个元素， *x* 和 *y* 从元素 *y* 中找到元素 *x* 的最近出现索引。

> **输入** : test_list = [2，4，5，7，8，6，3，8，7，2，0，9，4，9，4]，x = 4，y = 6
> **输出** : 1
> **解释** : 4 在 1，12，14 指数处找到，6 在第 5 指数处，最近的是第 1 指数。
> 
> **输入** : test_list = [2，4，5，7，8，6，3，8，7，2，0，9，4，9，4]，x = 7，y = 6
> **输出** : 3
> **解释** : 7 在第 3 和第 8 个指标，6 在第 5 个指标，最近的是第 3 个指标。

**方法:使用列表理解+循环+索引()**

在这里，我们使用列表理解找到 *y* 的所有索引，然后使用 *index()* 得到 *x* 的索引，使用 post 那个循环得到索引差，作为结果返回最近的索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Nearest occurrence of x from y in List
# Using list comprehension + loop + index()

# function to find index of nearest
# occurrence between two elements
def nearestOccurrenceIndex(test_list, x, y):

    # checking if both elements are present in list
    if x not in test_list or y not in test_list:
        return -1
    # getting indices of x
    x_idx = [idx for idx in range(len(test_list)) if test_list[idx] == x]

    # getting y index
    y_idx = test_list.index(y)

    # getting min_dist index
    min_dist = 1000000
    res = None
    for ele in x_idx:

        # checking for min ele, and updating index
        if abs(ele - y_idx) < min_dist:
            res = ele
            min_dist = abs(ele - y_idx)
    return res

# initializing list
input_list = [2, 4, 5, 7, 8, 6, 3, 8, 4, 2, 0, 9, 4, 9, 4]

# printing original list
print("The original list is : " + str(input_list))

# initializing x
x = 4

# initializing y
y = 6

# printing result
print("Minimum distance index: ", nearestOccurrenceIndex(input_list, x, y))
```

**输出:**

> 原列表为:【2、4、5、7、8、6、3、8、4、2、0、9、4、9、4】
> 最小距离指数:8
# Python 程序测试列表中所有元素是否相距最大 K

> 原文:[https://www . geeksforgeeks . org/python-如果列表中的所有元素都是 k 的最大值，则进行程序测试/](https://www.geeksforgeeks.org/python-program-to-test-if-all-elements-in-list-are-maximum-of-k-apart/)

给定一个数字列表，任务是编写一个 Python 程序来测试所有元素是否相距 K 的最大值。

**示例:**

> **输入:** test_list = [475，503，425，520，470，500]，K = 100
> 
> **输出:**真
> 
> **说明:**最大元素为 520，最小为 425，520-425 = 95，小于 100，因此元素在范围内。
> 
> **输入:** test_list = [475，503，425，540，470，500]，K = 100
> 
> **输出:**假
> 
> **说明:**最大元素为 540，最小为 425，520-425 = 115，大于 100，因此元素不在范围内。

**方法#1:使用** [**排序()**](https://www.geeksforgeeks.org/sort-in-python/)

在本例中，我们执行对元素进行排序的任务，以获得可使用 sort()访问的最小和最大元素。下一步是获取它们之间的差异，如果小于范围，则返回 True。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if all elements are in range size
# Using sort()

# initializing list
test_list = [475, 503, 425, 520, 470, 500]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 100

# sorting list
test_list.sort()

# checking if greater than range
res = test_list[-1] - test_list[0] < K

# printing result
print("Are elements in range ? : " + str(res))
```

**输出:**

```
The original list is : [475, 503, 425, 520, 470, 500]
Are elements in range ? : True
```

**方法 2:使用**[**min()**](https://www.geeksforgeeks.org/python-min-function/)**+**[**max()**](https://www.geeksforgeeks.org/python-max-function/)

使用 min()和 max()分别获取最小和最大元素，而不是改变排序或原始列表，两者之间的差异得到所需的结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if all elements are in range size
# Using min() + max()

# initializing list
test_list = [475, 503, 425, 520, 470, 500]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 100

# using min() and max() rather than
# changing order
res = max(test_list) - min(test_list) < K

# printing result
print("Are elements in range ? : " + str(res))
```

**输出:**

```
The original list is : [475, 503, 425, 520, 470, 500]
Are elements in range ? : True
```
# Python 程序删除带有自定义列表元素的行

> 原文:[https://www . geeksforgeeks . org/python-带自定义列表元素的程序删除行/](https://www.geeksforgeeks.org/python-program-to-remove-row-with-custom-list-element/)

给定一个矩阵，这里的任务是编写一个 Python 程序，从自定义列表中删除包含任何元素的行，然后显示结果。

**示例:**

> **输入** : test_list = [[5，3，1]，[7，8，9]，[1，10，22]，[12，18，21]]，check_list = [3，10，19，29，20，15]
> **输出** : [[7，8，9]，[12，18，21]]
> **解释** : [5，3，1]行在自定义列表中有 3 个
> 
> **输入** : test_list = [[5，3，1]，[7，8，19]，[1，10，22]，[12，18，20]]，check_list = [3，10，19，29，20，15]
> **输出** : []
> **说明:**所有行都有自定义列表中的一些元素，因此省略。

**方法 1:** 使用[任意()](https://www.geeksforgeeks.org/python-any-function/)和[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们执行检查自定义列表中的任何元素的任务，以使用 any()检查行，如果在行中找到自定义列表中的任何元素，则使用列表理解来省略行。

**示例:**

## 蟒蛇 3

```
# initializing Matrix
test_list = [[5, 3, 1], [7, 8, 9], [1, 10, 22], [12, 18, 21]]

# printing original list
print("The original list is : " + str(test_list))

# initializing custom list
check_list = [3, 10, 19, 29, 20, 15]

# list comprehension used to omit rows from matrix
# any() checks for any element found from check list
res = [row for row in test_list if not any(el in row for el in check_list)]

# printing result
print("The omitted rows matrix : " + str(res))
```

**输出:**

> 原来的名单是:[[5，3，1]，[7，8，9]，[1，10，22]，[12，18，21]]
> 
> 省略的行矩阵:[[7，8，9]，[12，18，21]]

**方法 2 :** 使用滤波器()，λ和[任意()](https://www.geeksforgeeks.org/python-any-function/)

与上述方法类似，唯一的区别是 filter()和 lambda 函数用于执行从结果中过滤掉或省略矩阵中的行的任务。

**示例:**

## 蟒蛇 3

```
# initializing Matrix
test_list = [[5, 3, 1], [7, 8, 9], [1, 10, 22], [12, 18, 21]]

# printing original list
print("The original list is : " + str(test_list))

# initializing custom list
check_list = [3, 10, 19, 29, 20, 15]

# filter() used to perform filtering
# any() checks for any element found from check list
res = list(filter(lambda row: not any(
    el in row for el in check_list), test_list))

# printing result
print("The omitted rows matrix : " + str(res))
```

**输出:**

> 原来的名单是:[[5，3，1]，[7，8，9]，[1，10，22]，[12，18，21]]
> 
> 省略的行矩阵:[[7，8，9]，[12，18，21]]
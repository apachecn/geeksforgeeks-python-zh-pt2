# Python 程序打印列表中给定元素的倍数的元素

> 原文:[https://www . geesforgeks . org/python-程序-打印-元素-列表中给定元素的倍数/](https://www.geeksforgeeks.org/python-program-to-print-elements-which-are-multiples-of-elements-given-in-a-list/)

给定一个列表，这里的任务是编写一个 Python 程序来提取自定义列表中所有元素的倍数。

> **输入** : test_list = [4，24，8，10，12，23]，div_list = [6，4]
> **输出** : [24，12]
> **解释** : 24 和 12 均除 6 和 4。
> 
> **输入** : test_list = [4，24，8，10，12，23]，div_list = [6，4，7]
> **输出** : []
> **解释**:无元素除 6，4，7。

**方法 1:** 使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)和[全部()](https://www.geeksforgeeks.org/any-all-in-python/)

在本例中，我们使用%运算符和 all()执行检查所有元素是否为多个的任务。列表理解用于遍历所有元素。

## 蟒蛇 3

```py
# initializing List
test_list = [4, 24, 8, 10, 12, 23]

# printing original list
print("The original list is : " + str(test_list))

# initializing divisor list
div_list = [6, 4]

# using all() to test for all elements
res = [ele for ele in test_list if all(ele % j == 0 for j in div_list)]

# printing result
print("All elements multiple of divisor list : " + str(res))
```

**输出:**

> 原来的名单是:[4，24，8，10，12，23]
> 
> 除数列表的所有元素倍数:[24，12]

**方法二:**使用[滤镜()](https://www.geeksforgeeks.org/filter-in-python/)、[λ](https://www.geeksforgeeks.org/python-lambda/)和[全部()](https://www.geeksforgeeks.org/any-all-in-python/)

在本例中，我们使用 filter()和 lambda 执行过滤任务，其余所有操作都像上面的方法一样执行。

## 蟒蛇 3

```py
# initializing List
test_list = [4, 24, 8, 10, 12, 23]

# printing original list
print("The original list is : " + str(test_list))

# initializing divisor list
div_list = [6, 4]

# using all() to test for all elements
# using filter() and lambda to perform filtering
res = list(filter(lambda ele: all(ele % j == 0 for j in div_list), test_list))

# printing result
print("All elements multiple of divisor list : " + str(res))
```

**输出:**

> 原来的名单是:[4，24，8，10，12，23]
> 
> 除数列表的所有元素倍数:[24，12]
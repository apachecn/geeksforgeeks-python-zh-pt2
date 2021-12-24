# Python–删除非递增元素

> 原文:[https://www . geesforgeks . org/python-remove-非递增-elements/](https://www.geeksforgeeks.org/python-remove-non-increasing-elements/)

给定一个列表，我们的任务是编写一个 Python 程序，从列表中移除所有不增加的元素。

> **输入:** test_list = [5，3，4，5，7，3，9，10，3，10，12，13，3，16，1]
> 
> **输出:**【5、5、5、7、9、10、10、12、13、16】
> 
> **解释:** 3、4 省略为 5，(更大的元素)发生在它们之前。适用于所有其他省略的元素。
> 
> **输入:** test_list = [5，3，4，5，7，3，9]
> 
> **输出:**【5，5，5，7，9】
> 
> **解释:** 3、4 省略为 5，(更大的元素)发生在它们之前。适用于所有其他省略的元素。

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/python-for-loops/)

在这种情况下，在填充下一个列表之前，先检查上一个元素，如果找到更大的元素，就追加它，否则就使用循环删除它。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove non-increasing elements
# Using loop

# initializing list
test_list = [5, 3, 4, 5, 7, 3, 9, 10, 3, 10, 12, 13, 3, 16, 1]

# printing original list
print("The original list is : " + str(test_list))

res = [test_list[0]]
for ele in test_list:

    # checking preceding element to decide for greater element
    if ele >= res[-1]:
        res.append(ele)

# printing result
print("The list after removing non-increasing elements : " + str(res))
```

**输出:**

> 原来的名单是:[5，3，4，5，7，3，9，10，3，10，12，13，3，16，1]
> 
> 删除非递增元素后的列表:[5，5，5，7，9，10，10，12，13，16]

**方法 2:使用** [**列表理解**](https://www.geeksforgeeks.org/comprehensions-in-python/)**+**[**max**](https://www.geeksforgeeks.org/python-max-function/)**+**[zip](https://www.geeksforgeeks.org/zip-in-python/)**()+**[T21】累加](https://www.geeksforgeeks.org/python-itertools-accumulate/)

在这种情况下，最大元素被压缩到当前元素，然后使用列表理解来检查是否出现比当前元素更高的元素，如果是，则添加它，否则在运行时迭代的结果中省略新元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove non-increasing elements
# Using list comprehension + max + zip() + accumulate
from itertools import accumulate

# initializing list
test_list = [5, 3, 4, 5, 7, 3, 9, 10, 3, 10, 12, 13, 3, 16, 1]

# printing original list
print("The original list is : " + str(test_list))

# checking for each element with curr maximum computed using zip
res = [idx for idx, ele in zip(test_list, accumulate(test_list, max)) if idx == ele]

# printing result
print("The list after removing non-increasing elements : " + str(res))
```

**输出:**

> 原来的名单是:[5，3，4，5，7，3，9，10，3，10，12，13，3，16，1]
> 
> 删除非递增元素后的列表:[5，5，5，7，9，10，10，12，13，16]
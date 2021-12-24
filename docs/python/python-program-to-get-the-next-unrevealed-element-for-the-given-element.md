# Python 程序获取给定元素的下一个未显示元素

> 原文:[https://www . geesforgeks . org/python-program-to-get-the-next-under-element-for-给定元素/](https://www.geeksforgeeks.org/python-program-to-get-the-next-unrevealed-element-for-the-given-element/)

给定一个数字列表和列表中的一个特定元素，任务是编写一个 Python 程序，让下一个未显示的元素出现在给定元素的第一个出现处，即直到给定元素出现才出现的元素。

**示例:**

> **输入:** test_list = [3，4，6，6，3，2，3，5，6，3，4，5，5，3，6]，nex_to_ele = 6
> 
> **输出:** 2
> 
> **说明:**在上面的列表中有 2、3、4、5 和 6 是元素，因为 nex_to_ele 是 6，其第一次出现在索引 2 处，在此之前只有 3 和 4 出现，所以未显示的元素是 2 和 5，其中未显示的元素 2 是第一次出现 6 之后的下一个。因此，2 是列表中下一个未显示的元素 6。
> 
> **输入:** test_list = [3，4，6，6，3，2，3，5，6，3，4，5，5，3，6]，nex_to_ele = 3
> 
> **输出:** 4
> 
> **解释:**3 的下一个不同的未显示元素是 4，因为 3 出现在索引 0 处。因此，列表中没有一个元素出现在 3 之前，而 4 是 3 之后的下一个元素。

**方法#1:使用** [**设置()**](https://www.geeksforgeeks.org/python-sets/) **+** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/) **+** [**索引()**](https://www.geeksforgeeks.org/python-list-index/)

在这种情况下，使用 set()和 sorted()将列表转换为保持顺序的唯一元素列表。然后使用 index()获取 number 的索引，结果列表中的下一个元素就是所需的元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Next different element in list
# Using set() + sorted() + index()

# initializing list
test_list = [3, 4, 6, 6, 3, 2, 3, 5, 6, 3, 4, 5, 5, 3, 6]

# printing original list
print("The original list is : " + str(test_list))

# initializing element
nex_to_ele = 6

# sorting removing duplicated keeping order
temp = sorted(set(test_list), key=lambda sub: test_list.index(sub))

# getting next index
num_idx = temp.index(nex_to_ele)

# checking for last index for overflow
if num_idx == len(temp) - 1:
    res = None

# getting next index as result
else:
    res = temp[num_idx + 1]

# printing result
print("Next different element : " + str(res))
```

**输出:**

> 原来的名单是:[3，4，6，6，3，2，3，5，6，3，4，5，5，3，6]
> 
> 下一个不同的元素:2

**方法#2:使用**[**next()**](https://www.geeksforgeeks.org/python-next-method/)**+**[**ITER()**](https://www.geeksforgeeks.org/python-iter-method/)**+**[**sorted()**](https://www.geeksforgeeks.org/sorted-function-python/)**+**[T21】set()](https://www.geeksforgeeks.org/python-sets/)

在这种情况下，我们不使用 index()来获取元素索引，而是使用用户迭代器方法来递增到下一个迭代器，直到找到元素。它的下一个元素是结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Next different element in list
# Using next() + iter() + sorted() + set()

# initializing list
test_list = [3, 4, 6, 6, 3, 2, 3, 5, 6, 3, 4, 5, 5, 3, 6]

# printing original list
print("The original list is : " + str(test_list))

# initializing element
nex_to_ele = 6

# sorting removing duplicated keeping order
temp = sorted(set(test_list), key=lambda sub: test_list.index(sub))

temp_itr = iter(temp)
flag = 0
for idx in range(0, len(temp)):

    # if last element is element to find
    if idx == len(temp) - 1:
        flag = 1

    # breaking when element is found
    if next(temp_itr) == nex_to_ele:
        break

if flag:
    res = None
else:

    # next element is answer
    res = next(temp_itr)

# printing result
print("Next different element : " + str(res))
```

**输出:**

> 原来的名单是:[3，4，6，6，3，2，3，5，6，3，4，5，5，3，6]
> 
> 下一个不同的元素:2
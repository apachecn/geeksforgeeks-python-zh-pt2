# Python 程序使用另一个列表中的值来屏蔽一个列表

> 原文:[https://www . geesforgeks . org/python-program-to-mask-a-list-使用来自另一个列表的值/](https://www.geeksforgeeks.org/python-program-to-mask-a-list-using-values-from-another-list/)

给定两个列表，任务是编写一个 python 程序，将其他列表中的元素标记为 1，否则标记为 0。

> **输入:** test_list = [5，2，1，9，8，0，4]，search_list = [1，10，8，3，9]
> 
> **输出:**【0，0，1，1，1，0，0】
> 
> **说明:** 1、9、8 出现在 test_list 的位置 2、3、4，被 1 屏蔽。其余部分被 0 屏蔽。
> 
> **输入:** test_list = [5，2，1，19，8，0，4]，search_list = [1，10，8，3，9]
> 
> **输出:**【0，0，1，0，1，0，0】
> 
> **说明:** 1、8 出现在 test_list 的位置 2、4，被 1 屏蔽。其余部分被 0 屏蔽。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在本文中，我们通过搜索列表和用于使用列表理解检查合成的 In 运算符进行迭代，并为存在指定 1，为不存在指定 0。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Boolean composition mask in list
# Using list comprehension

# initializing list
test_list = [5, 2, 1, 9, 8, 0, 4]

# printing original list
print("The original list is : " + str(test_list))

# initializing search list
search_list = [1, 10, 8, 3, 9]

# list comprehension iteration and in operator
# checking composition
res = [1 if ele in search_list else 0 for ele in test_list]

# printing result
print("The Boolean Masked list : " + str(res))
```

**输出:**

```py
The original list is : [5, 2, 1, 9, 8, 0, 4]
The Boolean Masked list : [0, 0, 1, 1, 1, 0, 0]
```

**方法二:使用** [**设定()**](https://www.geeksforgeeks.org/python-sets/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，使用 set()从搜索列表中删除重复的元素以减少搜索空间。其余所有操作与上述方法类似。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Boolean composition mask in list
# Using set() + list comprehension

# initializing list
test_list = [5, 2, 1, 9, 8, 0, 4]

# printing original list
print("The original list is : " + str(test_list))

# initializing search list
search_list = [1, 10, 8, 3, 9]

# list comprehension iteration and in operator
# checking composition
# set() removes duplicates
res = [1 if ele in set(search_list) else 0 for ele in test_list]

# printing result
print("The Boolean Masked list : " + str(res))
```

**输出:**

```py
The original list is : [5, 2, 1, 9, 8, 0, 4]
The Boolean Masked list : [0, 0, 1, 1, 1, 0, 0]
```
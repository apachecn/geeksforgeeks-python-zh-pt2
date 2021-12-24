# Python 程序，仅从列表中提取具有特定数字的数字

> 原文:[https://www . geeksforgeeks . org/python-program-to-extract-only-the-numbers-from-list-其中有一些特定的数字/](https://www.geeksforgeeks.org/python-program-to-extract-only-the-numbers-from-a-list-which-have-some-specific-digits/)

给定元素列表，提取带有特定数字的数字。

> **输入**:test _ list =【3456，23，128，235，982】，dig _ list =【2，3，5，4】
> **输出**:【23，235】
> **解释** : 2，3 和 2，3，5 在数字列表中，因此提取元素。
> **输入** : test_list = [3456，23，28，235，982]，dig_list = [2，3，5，4，8]
> **输出**:【23，28，235】
> **解释** : 2，3；2、8 和 2、3、5 在数字列表中，因此是提取的元素。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**全部()**](https://www.geeksforgeeks.org/any-all-in-python/)

在这种情况下，我们根据目标列表中的元素检查每个元素的数量是否存在，如果在列表中找到所有元素，则返回元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Elements with specific digits
# Using list comprehension + all()

# initializing list
test_list = [345, 23, 128, 235, 982]

# printing original list
print("The original list is : " + str(test_list))

# initializing digit list 
dig_list = [2, 3, 5, 4]

# checking for all digits using all()
res = [sub for sub in test_list if all(int(ele) in dig_list for ele in str(sub))]

# printing result 
print("Extracted elements : " + str(res))
```

**输出:**

```
The original list is : [345, 23, 128, 235, 982]
Extracted elements : [345, 23, 235]
```

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)**+all()**

在这种情况下，使用 filter() + lambda 对元素进行过滤，all()用于检查其他列表中的所有数字。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Elements with specific digits
# Using filter() + lambda + all()

# initializing list
test_list = [345, 23, 128, 235, 982]

# printing original list
print("The original list is : " + str(test_list))

# initializing digit list 
dig_list = [2, 3, 5, 4]

# filter() used to filter from logic 
res = list(filter(lambda sub : all(int(ele) in dig_list for ele in str(sub)), test_list))

# printing result 
print("Extracted elements : " + str(res))
```

**输出:**

```
The original list is : [345, 23, 128, 235, 982]
Extracted elements : [345, 23, 235]
```
# Python–从列表中删除所有元素都为无的元组

> 原文:[https://www . geesforgeks . org/python-从列表中移除元组-将每个元素都视为无/](https://www.geeksforgeeks.org/python-remove-tuples-from-the-list-having-every-element-as-none/)

给定元组列表，移除所有无值的元组。

> **输入** : test_list = [(无，2)，(无，无)，(3，4)，(12，3)，(无)，]
> **输出** : [(无，2)，(3，4)，(12，3)]
> **解释**:所有无元组均被移除。
> 
> **输入** : test_list = [(无，无)，(无，无)，(3，4)，(12，3)，(无)，]
> **输出** : [(3，4)，(12，3)]
> **解释**:所有无元组被移除。

**方法#1:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们使用 all()来检查所有的 None 值以进行丢弃，列表理解执行迭代任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove None Tuples from List
# Using all() + list comprehension

# initializing list
test_list = [(None, 2), (None, None), (3, 4), (12, 3), (None, )]

# printing original list
print("The original list is : " + str(test_list))

# negating result for discarding all None Tuples
res = [sub for sub in test_list if not all(ele == None for ele in sub)]

# printing result 
print("Removed None Tuples : " + str(res))
```

**输出:**

> 原始列表为:[(无，2)，(无，无)，(3，4)，(12，3)，(无)，]
> 删除的无元组:[(无，2)，(3，4)，(12，3)]

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+all()**

在该方法中，过滤无元组的任务是使用 filter()和 lambda 函数完成的，以使用 all()提供无检查功能。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove None Tuples from List
# Using filter() + lambda + all()

# initializing list
test_list = [(None, 2), (None, None), (3, 4), (12, 3), (None, )]

# printing original list
print("The original list is : " + str(test_list))

# filter() + lambda to drive logic of discarding tuples
res = list(filter(lambda sub : not all(ele == None for ele in sub), test_list))

# printing result 
print("Removed None Tuples : " + str(res))
```

**输出:**

> 原始列表为:[(无，2)，(无，无)，(3，4)，(12，3)，(无)，]
> 删除的无元组:[(无，2)，(3，4)，(12，3)]
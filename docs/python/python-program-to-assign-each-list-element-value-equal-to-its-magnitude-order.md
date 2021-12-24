# Python 程序分配每个列表元素值等于其数量级

> 原文:[https://www . geesforgeks . org/python-program-to-assignment-每个列表-元素-值-等于其数量级/](https://www.geeksforgeeks.org/python-program-to-assign-each-list-element-value-equal-to-its-magnitude-order/)

给定一个列表，任务是编写一个 Python 程序，将每个元素值指定为与其数量级相等。

> **输入:** test_list = [8，3，5，8，1，5，4]
> 
> **输出:**【4，1，3，4，0，3，2】
> 
> **说明:** 8 是第 5 个最大值，因此分配了 4[从第 0 个索引开始]。
> 
> **输入:** test_list = [3，2，0]
> 
> **输出:**【2，1，0】
> 
> **说明:** 3 是第三个最大值，因为分配了 2。

**方法一:使用** [**设置()**](https://www.geeksforgeeks.org/python-set-method/)**+**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)**+**[**dict()**](https://www.geeksforgeeks.org/python-dictionary/)T18】+[T21】列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在本例中，我们使用 zip()执行将集合转换列表的排序索引映射到值的任务，然后转换到映射到值的值字典。那么列表理解习惯于在列表中排序。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Relative Size Ordering 
# Using set() + zip() + sorted() + dict() + list comprehension

# initializing list
test_list = [8, 3, 5, 8, 1, 5, 4]

# printing original list
print("The original list is : " + str(test_list))

# assigning order to each value
ord_dict = dict(zip(list(set(test_list)),
                    range(len(set(test_list)))))

# mapping element with ordered value
res = [ord_dict[ele] for ele in test_list]

# printing result
print("Relative size ordered list : " + str(res))
```

**输出:**

```
The original list is : [8, 3, 5, 8, 1, 5, 4]
Relative size ordered list : [4, 1, 3, 4, 0, 3, 2]
```

**方法二:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/) **+** [**集合()**](https://www.geeksforgeeks.org/python-set-method/) **+** [**索引()**](https://www.geeksforgeeks.org/python-list-index/)**+**[T21】列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们执行转换到集合然后排序的任务，索引到顺序的映射使用 index()和列表理解来完成。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Relative Size Ordering 
# Using sorted() + set() + index() + list comprehension

# initializing list
test_list = [8, 3, 5, 8, 1, 5, 4]

# printing original list
print("The original list is : " + str(test_list))

# getting order
ord_dict = list(set(test_list))

# mapping index
res = [ord_dict.index(ele) for ele in test_list]

# printing result
print("Relative size ordered list : " + str(res))
```

**输出:**

```
The original list is : [8, 3, 5, 8, 1, 5, 4]
Relative size ordered list : [4, 1, 3, 4, 0, 3, 2]
```
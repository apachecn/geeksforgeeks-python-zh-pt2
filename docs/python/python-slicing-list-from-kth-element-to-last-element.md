# Python |从第 k 个元素到最后一个元素的切片列表

> 原文:[https://www . geesforgeks . org/python-slicing-list-from-kth-element-to-last-element/](https://www.geeksforgeeks.org/python-slicing-list-from-kth-element-to-last-element/)

Python [列表切片](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)从开始索引到*结束–1*对列表进行切片，指定为列表元素。因此，当我们需要对列表的最后一个元素进行切片时，这就很棘手了。尝试切片直到列表*大小+ 1* 出现错误。让我们讨论在列表切片中包含最后一个元素的方法。

**方法#1:使用无**
在列表切片过程中，给出所需的第一个索引 K，并指定“无”作为切片中的第二个参数，内部工作方式是从列表中的 K 开始对所有元素进行切片，直到包含它的末尾。

```py
# Python3 code to demonstrate 
# list slicing from K to end
# using None

# initializing list
test_list = [5, 6, 2, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# index to begin slicing
K = 2

# using None 
# to perform list slicing from K to end
res = test_list[K : None]

# printing result 
print ("The sliced list is : " +  str(res))
```

**Output:**

```py
The original list is : [5, 6, 2, 3, 9]
The sliced list is : [2, 3, 9]

```
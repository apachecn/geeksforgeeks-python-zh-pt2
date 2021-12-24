# Python 程序按第二项对元组列表进行排序

> 原文:[https://www . geesforgeks . org/python-程序-按第二项对元组列表进行排序/](https://www.geeksforgeeks.org/python-program-to-sort-a-list-of-tuples-by-second-item/)

给定一个元组列表，编写一个 Python 程序，按照每个元组的第二项对元组进行排序。

**示例:**

```
Input : [('for', 24), ('Geeks', 8), ('Geeks', 30)] 
Output : [('Geeks', 8), ('for', 24), ('Geeks', 30)]

Input : [('452', 10), ('256', 5), ('100', 20), ('135', 15)]
Output : [('256', 5), ('452', 10), ('135', 15), ('100', 20)]
```

**方法#1:** 使用[冒泡排序](https://www.geeksforgeeks.org/bubble-sort/)

使用冒泡排序技术，我们可以进行排序。请注意，每个元组都是给定列表中的一个元素。使用嵌套循环访问每个元组的第二个元素。这将执行就地排序方法。时间复杂度类似于冒泡排序，即 O(n^2).

```
# Python program to sort a list of tuples by the second Item

# Function to sort the list of tuples by its second item
def Sort_Tuple(tup): 

    # getting length of list of tuples
    lst = len(tup) 
    for i in range(0, lst): 

        for j in range(0, lst-i-1): 
            if (tup[j][1] > tup[j + 1][1]): 
                temp = tup[j] 
                tup[j]= tup[j + 1] 
                tup[j + 1]= temp 
    return tup 

# Driver Code 
tup =[('for', 24), ('is', 10), ('Geeks', 28), 
      ('Geeksforgeeks', 5), ('portal', 20), ('a', 15)] 

print(Sort_Tuple(tup)) 
```

**输出:**

```
[('Geeksforgeeks', 5), ('is', 10), ('a', 15), ('portal', 20), ('for', 24), ('Geeks', 28)]
```

**方法 2:** 使用[排序()方法](https://www.geeksforgeeks.org/sort-in-python/)

通过这种方法进行排序时，元组的实际内容会发生变化，就像前面的方法一样，会执行就地排序方法。

```
# Python program to sort a list of
# tuples by the second Item using sort() 

# Function to sort hte list by second item of tuple
def Sort_Tuple(tup): 

    # reverse = None (Sorts in Ascending order) 
    # key is set to sort using second element of 
    # sublist lambda has been used 
    tup.sort(key = lambda x: x[1]) 
    return tup 

# Driver Code 
tup = [('rishav', 10), ('akash', 5), ('ram', 20), ('gaurav', 15)] 

# printing the sorted list of tuples
print(Sort_Tuple(tup)) 
```

**输出:**

```
[('akash', 5), ('rishav', 10), ('gaurav', 15), ('ram', 20)]
```

**方法#3:** 使用[排序()方法](https://www.geeksforgeeks.org/sorted-function-python/)

Sorted()方法对列表进行排序，并且总是以排序的方式返回包含元素的列表，而不修改原始序列。它需要三个参数，其中两个是可选的，这里我们尝试使用这三个参数:

**Iterable :** 序列(列表、元组、字符串)或集合(字典、集合、frozenset)或任何其他需要排序的迭代器。
**键(可选):**用作键或排序比较基础的函数。
**反向(可选):**要按升序排序，我们可以忽略第三个参数，这是我们在本程序中所做的。如果设置为 true，则可迭代将按相反(降序)顺序排序，默认情况下设置为 false。

```
# Python program to sort a list of
# tuples by the second Item using sorted() 

# Function to sort the list by second item of tuple
def Sort_Tuple(tup): 

    # reverse = None (Sorts in Ascending order) 
    # key is set to sort using second element of 
    # sublist lambda has been used 
    return(sorted(tup, key = lambda x: x[1]))  

# Driver Code 
tup = [('rishav', 10), ('akash', 5), ('ram', 20), ('gaurav', 15)] 

# printing the sorted list of tuples
print(Sort_Tuple(tup)) 
```

**输出:**

```
[('akash', 5), ('rishav', 10), ('gaurav', 15), ('ram', 20)]
```
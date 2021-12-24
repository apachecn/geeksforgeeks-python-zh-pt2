# 按照每个元组中的最后一个元素对元组列表进行递增排序的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-sort-list-a-元组-按每个元组中最后一个元素的递增顺序/](https://www.geeksforgeeks.org/python-program-to-sort-a-list-of-tuples-in-increasing-order-by-the-last-element-in-each-tuple/)

任务是编写一个 Python 程序，按照每个元组中最后一个元素的递增顺序对元组列表进行排序。

```
Input: [(1, 3), (3, 2), (2, 1)]
Output: [(2, 1), (3, 2), (1, 3)]
Explanation: sort tuple based on the last digit of each tuple.

```

**方法#1:** 使用排序的()。

Sorted()方法对列表进行排序，并且总是以排序的方式返回包含元素的列表，而不修改原始序列。

**进场:**

*   从用户那里获取元组列表。
*   定义一个函数，返回元组列表中每个元组的最后一个元素。
*   以前一个函数为关键字定义另一个函数，并对列表进行排序。
*   打印排序列表。

## 蟒蛇 3

```
def last(n):
    return n[-1]  

def sort(tuples):
    return sorted(tuples, key=last)

a=[(1, 3), (3, 2), (2, 1)]
print("Sorted:")
print(sort(a))
```

**输出:**

```
Sorted:
[(2, 1), (3, 2), (1, 3)]

```

**方法#2:** 使用冒泡排序。

使用嵌套循环访问每个元组的最后一个元素。这将执行就地排序方法。时间复杂度类似于冒泡排序，即 O(n^2).

## 蟒蛇 3

```
# Python program to sort 
# a list of tuples by the second Item 

# Function to sort the list 
# of tuples by its second item 
def Sort_Tuple(tup):  

    # getting length of list of tuples 
    lst = len(tup)  
    for i in range(0, lst):  

        for j in range(0, lst-i-1):  
            if (tup[j][-1] > tup[j + 1][-1]):  
                temp = tup[j]  
                tup[j]= tup[j + 1]  
                tup[j + 1]= temp  
    return tup  

# Driver Code  
tup =[(1, 3), (3, 2), (2, 1)]

print(Sort_Tuple(tup))
```

**输出:**

```
[(2, 1), (3, 2), (1, 3)]

```

**方法#3:** 使用排序()。

sort()方法以特定的升序或降序对给定列表的元素进行排序。

## 蟒蛇 3

```
# Python program to sort a list of 
# tuples by the second Item using sort()  

# Function to sort hte list by second item of tuple 
def Sort_Tuple(tup):  

    # reverse = None (Sorts in Ascending order)  
    # key is set to sort using second element of  
    # sublist lambda has been used  
    tup.sort(key = lambda x: x[-1])  
    return tup  

# Driver Code  
tup = [(1, 3), (3, 2), (2, 1)]

# printing the sorted list of tuples 
print(Sort_Tuple(tup))  
```

**输出:**

```
[(2, 1), (3, 2), (1, 3)]

```
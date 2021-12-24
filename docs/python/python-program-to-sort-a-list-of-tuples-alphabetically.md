# Python 程序按字母顺序对元组列表进行排序

> 原文:[https://www . geesforgeks . org/python-程序-排序-元组列表-按字母顺序/](https://www.geeksforgeeks.org/python-program-to-sort-a-list-of-tuples-alphabetically/)

给定一个元组列表，编写一个 Python 程序，按照每个元组的第一项的字母顺序对元组进行排序。

**示例:**

```
Input: [("Amana", 28), ("Zenat", 30), ("Abhishek", 29), ("Nikhil", 21), ("B", "C")]
Output: [('Amana', 28), ('Abhishek', 29), ('B', 'C'), ('Nikhil', 21), ('Zenat', 30)]

Input: [("aaaa", 28), ("aa", 30), ("bab", 29), ("bb", 21), ("csa", "C")]
Output: [('aa', 30), ('aaaa', 28), ('bab', 29), ('bb', 21), ('csa', 'C')]

```

**方法 1:** 使用[冒泡排序](https://www.geeksforgeeks.org/bubble-sort/)T5】使用冒泡排序的技巧来进行排序。请注意，每个元组都是给定列表中的一个元素。使用嵌套循环访问每个元组的第一个元素。这将执行就地排序方法。时间复杂度类似于冒泡排序，即`O(n^2)`。

```
# Python program to sort a
# list of tuples alphabetically

# Function to sort the list of
# tuples

def SortTuple(tup):

    # Getting the length of list 
    # of tuples
    n = len(tup)

    for i in range(n):
        for j in range(n-i-1):

            if tup[j][0] > tup[j + 1][0]:
                tup[j], tup[j + 1] = tup[j + 1], tup[j]

    return tup

# Driver's code

tup = [("Amana", 28), ("Zenat", 30), ("Abhishek", 29),
        ("Nikhil", 21), ("B", "C")]

print(SortTuple(tup))
```

**输出:**

```
[('Abhishek', 29), ('Amana', 28), ('B', 'C'), ('Nikhil', 21), ('Zenat', 30)]

```

**方法 2:** 使用 [sort()方法](https://www.geeksforgeeks.org/sort-in-python/)
通过该方法进行排序时，元组的实际内容会发生变化，就像前面的方法一样，会执行排序的就地方法。

```
# Python program to sort a list of 
# tuples using sort()  

# Function to sort the list
def SortTuple(tup):  

    # reverse = None (Sorts in Ascending order)  
    # key is set to sort using first element of  
    # sublist lambda has been used  
    tup.sort(key = lambda x: x[0])  
    return tup  

# Driver's code

tup = [("Amana", 28), ("Zenat", 30), ("Abhishek", 29),
        ("Nikhil", 21), ("B", "C")]

print(SortTuple(tup))
```

**输出:**

```
[('Abhishek', 29), ('Amana', 28), ('B', 'C'), ('Nikhil', 21), ('Zenat', 30)]

```

**方法 3:** 使用[排序()方法](https://www.geeksforgeeks.org/sorted-function-python/)

`sorted()`方法是 list 类的一种方法，返回排序后的列表，不对原列表做任何改动。

```
# Python program to sort a list of 
# tuples using sorted()  

# Function to sort the list
def Sort_Tuple(tup):  

    # reverse = None (Sorts in Ascending order)  
    # key is set to sort using first element of  
    # sublist lambda has been used  
    return(sorted(tup, key = lambda x: x[0]))   

# Driver Code  
tup = [("Amana", 28), ("Zenat", 30), ("Abhishek", 29),
        ("Nikhil", 21), ("B", "C")]

# printing the sorted list of tuples 
print(Sort_Tuple(tup)) 
```

**输出:**

```
[('Abhishek', 29), ('Amana', 28), ('B', 'C'), ('Nikhil', 21), ('Zenat', 30)]

```
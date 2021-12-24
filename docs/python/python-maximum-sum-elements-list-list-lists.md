# Python |列表中列表元素的最大和

> 原文:[https://www . geesforgeks . org/python-max-sum-elements-list-list/](https://www.geeksforgeeks.org/python-maximum-sum-elements-list-list-lists/)

给定列表中的列表，求列表中列表元素的最大和。

示例:

```
Input :  [[1, 2, 3], [4, 5, 6], [10, 11, 12], [7, 8, 9]]
Output : 33 
Explanation: sum of all lists in the given list of lists are:
             list1 = 6, list2 = 15, list3 = 33, list4 = 24 
             so the maximum among these is of 

Input : [[3, 4, 5], [1, 2, 3], [0, 9, 0]]
Output : 12

```

**方法 1:遍历列表中的列表**

我们可以遍历列表中的列表，并对给定列表中的所有元素求和，通过 **max 函数**得到列表中所有元素的最大和。

```
# Python program to find the 
# list in a list of lists whose 
# sum of elements is the highest
# using traversal

def maximumSum(list1):
    maxi = 0

    # traversal in the lists
    for x in list1:
        sum = 0 
        # traversal in list of lists
        for y in x:
            sum+= y     
        maxi = max(sum, maxi) 

    return maxi

# driver code  
list1 = [[1, 2, 3], [4, 5, 6], [10, 11, 12], [7, 8, 9]]
print maximumSum(list1)
```

**输出:**

```
33

```

**方法二:遍历列表**

只在外部列表中遍历，使用 [sum()](https://www.geeksforgeeks.org/sum-function-python/) 函数对内部列表中的所有元素求和，求所有列表的和，得到所有计算的和的最大值。

```
# Python program to find the 
# list in a list of lists whose 
# sum of elements is the highest
# using sum and max function and traversal

def maximumSum(list1):
    maxi = 0
    # traversal
    for x in list1:
        maxi = max(sum(x), maxi)

    return maxi

# driver code  
list1 = [[1, 2, 3], [4, 5, 6], [10, 11, 12], [7, 8, 9]]
print maximumSum(list1)
```

**输出:**

```
33

```

**方法三:求和最大函数**

```
sum(max(list1, key=sum))
```

max()函数的上述语法允许我们使用**键=sum** 在列表中找到列表的和。 **max(list1，key=sum)** ，这将找到元素总和最大的列表，然后 **sum(max(list1，key = sum)】**将该列表的总和返回给我们。

```
# Python program to find the 
# list in a list of lists whose 
# sum of elements is the highest
# using sum and max function

def maximumSum(list1):
    return(sum(max(list1, key = sum)))

# driver code  
list1 = [[1, 2, 3], [4, 5, 6], [10, 11, 12], [7, 8, 9]]
print maximumSum(list1)
```

**输出:**

```
33

```
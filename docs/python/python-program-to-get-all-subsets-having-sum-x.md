# Python 程序获取所有具有和 x 的子集

> 原文:[https://www . geesforgeks . org/python-program-to-get-all-subset-having-sum-x/](https://www.geeksforgeeks.org/python-program-to-get-all-subsets-having-sum-x/)

给我们一个 n 个数字和一个 x 的列表，任务是编写一个 python 程序，找出列表中所有可能的子集，使它们的和为 x。

**示例:**

> **输入:** arr = [2，4，5，9]，x = 15
> 
> **输出:**【2，4，9】
> 
> 从给定的列表中加上 2、4 和 9 可以得到 15。
> 
> **输入:** arr = [10，20，25，50，70，90]，x = 80
> 
> **输出:**【10，70】
> 
>          [10, 20, 50]
> 
> 80 可以通过将 10 和 70 相加或从给定列表中添加 10、20 和 50 来获得。

**方法#1:**

这是一种蛮力方法。找到给定列表的所有可能的子集和，并检查和是否等于 x。使用这种方法的时间复杂度是 O(2^n)，这是相当大的。

## 蟒蛇 3

```py
# Python code with time complexity
# O(2^n)to print all subsets whose
# sum is equal to a given value
from itertools import combinations

def subsetSum(n, arr, x):

    # Iterating through all possible
    # subsets of arr from lengths 0 to n:
    for i in range(n+1):
        for subset in combinations(arr, i):

            # printing the subset if its sum is x:
            if sum(subset) == x:
                print(list(subset))

# Driver Code:
n = 6
arr = [10, 20, 25, 50, 70, 90]
x = 80
subsetSum(n, arr, x)
```

**输出:**

```py
[10, 70]
[10, 20, 50]
```

**接近#2:**

[在中间相遇](https://www.geeksforgeeks.org/meet-in-the-middle/)是一种将搜索空间分成两个大小相等的部分，对这两个部分分别进行搜索，然后组合搜索结果的技术。使用这种技术，两次搜索可能比一次大型搜索需要更少的时间，并将时间复杂性从 O(2^n 转移到 O(2^(n/2)).

## 蟒蛇 3

```py
# Efficient Python code to
# print all subsets whose sum
# is equal to a given value
from itertools import combinations

def subsetSum(li, comb, sums):
    # Iterating through all subsets of
    # list li from length 0 to length of li:
    for i in range(len(li)+1):
        for subset in combinations(li, i):

            # Storing all the subsets in list comb:
            comb.append(list(subset))

            # Storing the subset sums in list sums:
            sums.append(sum(subset))

def calcSubsets(n, arr, x):

    # Dividing the list arr into two lists
    # arr1 and arr2 of about equal sizes
    # by slicing list arr about index n//2:
    arr1, arr2 = arr[:n//2], arr[n//2:]

    # Creating empty lists comb1 and sums1
    # to run the subsetSum function and
    # store subsets of arr1 in comb1
    # and the subset sums in sums1:
    comb1, sums1 = [], []
    subsetSum(arr1, comb1, sums1)

    # Creating empty lists comb2 and sums2
    # to run the subsetSum function and
    # store subsets of arr2 in comb2
    # and the subset sums in sums2:
    comb2, sums2 = [], []
    subsetSum(arr2, comb2, sums2)

    # Iterating i through the indices of sums1:
    for i in range(len(sums1)):

        # Iterating j through the indices of sums2:
        for j in range(len(sums2)):

            # If two elements (one from sums1
            # and one from sums2) add up to x,
            # the combined list of elements from
            # corresponding subsets at index i in comb1
            # and j in comb2 gives us the required answer:
            if sums1[i] + sums2[j] == x:
                print(comb1[i] + comb2[j])

# Driver Code:
n = 6
arr = [10, 20, 25, 50, 70, 90]
x = 80
calcSubsets(n, arr, x)
```

**输出:**

```py
[10, 70]
[10, 20, 50]
```
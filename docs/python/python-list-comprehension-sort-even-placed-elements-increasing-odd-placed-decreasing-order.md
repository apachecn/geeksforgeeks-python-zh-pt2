# Python 列表理解|按升序排列偶数元素，按降序排列奇数元素

> 原文:[https://www . geesforgeks . org/python-list-领悟-排序-偶数-放置-元素-递增-奇数-放置-递减-顺序/](https://www.geeksforgeeks.org/python-list-comprehension-sort-even-placed-elements-increasing-odd-placed-decreasing-order/)

给我们一个 n 个不同数字的数组，任务是将所有偶数按递增顺序排序，奇数按递减顺序排序。修改后的数组应该包含所有已排序的偶数，后跟反向排序的奇数。

请注意，第一个元素被认为是偶数，因为它的索引为 0。

示例:

```py
Input:  arr[] = {0, 1, 2, 3, 4, 5, 6, 7}
Output: arr[] = {0, 2, 4, 6, 7, 5, 3, 1}
Even-place elements : 0, 2, 4, 6
Odd-place elements : 1, 3, 5, 7
Even-place elements in increasing order : 
0, 2, 4, 6
Odd-Place elements in decreasing order : 
7, 5, 3, 1

Input: arr[] = {3, 1, 2, 4, 5, 9, 13, 14, 12}
Output: {2, 3, 5, 12, 13, 14, 9, 4, 1}
Even-place elements : 3, 2, 5, 13, 12
Odd-place elements : 1, 4, 9, 14
Even-place elements in increasing order : 
2, 3, 5, 12, 13
Odd-Place elements in decreasing order : 
14, 9, 4, 1

```

这个问题我们已经有了解决方案，请参考[按照递增顺序排列偶数元素，按照递减顺序排列奇数元素](https://www.geeksforgeeks.org/sort-even-placed-elements-increasing-odd-placed-decreasing-order/)链接。我们可以使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)在 python 中快速解决这个问题。方法很简单，

1.  将原始列表分成两部分，一部分包含所有偶数索引元素，一部分包含所有奇数索引元素。
2.  现在按升序对包含所有偶数索引元素的列表进行排序，按降序对包含所有奇数索引元素的列表进行排序。现在将它们连接起来。

```py
# Function to Sort even-placed elements 
# in increasing and odd-placed in decreasing
# order

def evenOddSort(input):

     # separate even odd indexed elements list
     evens = [ input[i] for i in range(0,len(input)) if i%2==0 ] 
     odds = [ input[i] for i in range(0,len(input)) if i%2!=0 ] 

     # sort evens in ascending and odds in 
     # descending using sorted() method
     print (sorted(evens) + sorted(odds,reverse=True))

# Driver program
if __name__ == "__main__":
    input = [0, 1, 2, 3, 4, 5, 6, 7]
    evenOddSort(input)
```

输出:

```py
[0, 2, 4, 6, 7, 5, 3, 1]

```
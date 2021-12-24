# Python 程序从列表中找到 N 个最大的元素

> 原文:[https://www . geesforgeks . org/python-program-to-find-n-最大元素-来自列表/](https://www.geeksforgeeks.org/python-program-to-find-n-largest-elements-from-a-list/)

给定一个整数列表，任务是找到 N 个最大的元素，假设列表的大小大于或等于 N

**示例:**

```py
Input : [4, 5, 1, 2, 9] 
        N = 2
Output :  [9, 5]

Input : [81, 52, 45, 10, 3, 2, 96] 
        N = 3
Output : [81, 96, 52]

```

一个简单的解决方案遍历给定的列表 N 次。在每次遍历中，找到最大值，将其添加到结果中，并将其从列表中移除。下面是实现:

```py
# Python program to find N largest
# element from given list of integers

# Function returns N largest elements
def Nmaxelements(list1, N):
    final_list = []

    for i in range(0, N): 
        max1 = 0

        for j in range(len(list1)):     
            if list1[j] > max1:
                max1 = list1[j];

        list1.remove(max1);
        final_list.append(max1)

    print(final_list)

# Driver code
list1 = [2, 6, 41, 85, 0, 3, 7, 6, 10]
N = 2

# Calling the function
Nmaxelements(list1, N)
```

输出:

```py
[85, 41]
```

时间复杂度:O(N * size)，其中 size 是给定列表的大小。
方法二:

```py
# Python program to find N largest
# element from given list of integers

l = [1000,298,3579,100,200,-45,900]
n = 4

l.sort()
print(l[-n:])
```

输出:

```py
[-45, 100, 200, 298, 900, 1000, 3579]
Find the N largest element: 4
[298, 900, 1000, 3579]

```

请参考[一个数组中 k 个最大(或最小)的元素](https://www.geeksforgeeks.org/k-largestor-smallest-elements-in-an-array/)来获得这个问题更有效的解决方案。
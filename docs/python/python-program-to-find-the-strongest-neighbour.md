# 寻找最强邻居的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-find-最强邻居/](https://www.geeksforgeeks.org/python-program-to-find-the-strongest-neighbour/)

给定一个由 N 个正整数组成的数组 arr[]。任务是找到数组中每个相邻对的最大值。

**示例:**

```
Input: 1 2 2 3 4 5
Output: 2 2 3 4 5

Input: 5 5
Output: 5

```

**进场:**

1.  读取输入数组，即 arr1。
2.  对于 i=1 至 sizeofarray-1
    *   找出 arr1[i]和 arr1[i-1]之间的最大值。
    *   将上述值存储在另一个数组中，即 arr2。
3.  打印 arr2 的值。

下面是实现。

## 蟒蛇 3

```
# define a function for finding
# the maximum for adjacent
# pairs in the array
def maximumAdjacent(arr1, n):

      # array to store the max 
    # value between adjacent pairs
    arr2 = []  

    # iterate from 1 to n - 1
    for i in range(1, n):

        # find max value between 
        # adjacent  pairs gets 
        # stored in r
        r = max(arr1[i], arr1[i-1])

        # add element 
        arr2.append(r)

    # printing the elements
    for ele in arr2 :
        print(ele,end=" ")

if __name__ == "__main__" :

  # size of the input array
  n = 6  

  # input array
  arr1 = [1,2,2,3,4,5]

  # function calling
  maximumAdjacent(arr1, n)
```

**输出:**

```
2 2 3 4 5

```
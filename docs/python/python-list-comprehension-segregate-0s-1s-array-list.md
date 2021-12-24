# Python 列表理解|在数组列表中分隔 0 和 1

> 原文:[https://www . geesforgeks . org/python-list-intensity-separate-0s-1s-array-list/](https://www.geeksforgeeks.org/python-list-comprehension-segregate-0s-1s-array-list/)

给你一个随机排列的 0 和 1 的数组。将阵列左侧的 0 和右侧的 1 分开。

示例:

```
Input  :  arr = [0, 1, 0, 1, 0, 0, 1, 1, 1, 0] 
Output :  [0, 0, 0, 0, 0, 1, 1, 1, 1, 1] 

```

对于这个问题我们已经有了解决方案，请参考[在一个数组](https://www.geeksforgeeks.org/segregate-0s-and-1s-in-an-array-by-traversing-array-once/)链接中分隔 0 和 1。我们可以使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)在 Python 中快速解决这个问题。遍历给定的列表，分离出两个不同的列表，一个包含所有 0，另一个包含所有 1。现在将这两个列表连接在一起。

```
# Function to Segregate 0's and 1's in an array list

def segregate(arr):
    res = ([x for x in arr if x==0] + [x for x in arr if x==1])
    print(res)

# Driver program
if __name__ == "__main__":
    arr = [0, 1, 0, 1, 0, 0, 1, 1, 1, 0] 
    segregate(arr)
```

输出:

```
[0, 0, 0, 0, 0, 1, 1, 1, 1, 1] 

```
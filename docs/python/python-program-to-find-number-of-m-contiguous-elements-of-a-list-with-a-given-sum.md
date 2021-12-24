# Python 程序，用于查找给定总和的列表中 m 个连续元素的数量

> 原文:[https://www . geesforgeks . org/python-program-to-find-number-of-m-contined-elements-of-list-of-a-a-给定-sum/](https://www.geeksforgeeks.org/python-program-to-find-number-of-m-contiguous-elements-of-a-list-with-a-given-sum/)

给定一个列表“L”、一个总和“S”和一次要取的元素数“m”。任务是找出通过添加任意 m 个连续元素可以找到和 s 的多少种方法。

**例:**

```
Input : 
1 2 1 3 2
3 2

Output :
2
Input :
1 1 1 1 1 1
3 2
Output :
0

```

例如 1，我们必须借助列表中任意两个连续的元素找到和 3。这可以通过两种方式完成 1+2 和 2+1，所以答案是 2

**方法一:(简单)**

从开始，我们选择前 m 个元素，如果 sum = s，则找到它们的和，然后将计数增加 1，将索引位置增加 1 选择下 m 个元素，并重复相同的操作，直到覆盖整个列表。

```
# Python program to find number of
# m contiguous elements of a list 
# with sum s

def SearchWay(l, s, m):

    # initialise sum and
    # count to 0 
    sum1 = 0
    count = 0

    # iterate from start of
    # list to end
    for i in range (len(l)-m + 1):

        # get sum f m elements 
        # starting from index i 
        for j in range (i, i + m):
            sum1 += l[j]

        # if the sum of elements equal
        # s increment count 
        if sum1 == s:
            count += 1

        sum1 = 0

    return count

# Driver's code
l = [1, 2, 1, 3, 2]
s = 3 
m = 2

ans = SearchWay(l, s, m)
print(ans)
```

**输出:**

```
2

```

**时间复杂度:**最坏情况下的 O(n^2)。

**方法二:(高效)**

将变量索引初始化为 0，curr_sum 作为第一个元素。index 表示连续元素的计数，curr_sum 表示当前索引元素的总和。从第二个元素开始，将所有元素逐个添加到 curr_sum 中。如果 curr_sum 等于 sum，而 index 等于 m，那么 count 的值增加 1。如果索引超过 m，则删除尾随元素并将索引初始化为 m-1。

```
# Python program to find number of
# m contiguous elements of a list 
# with sum s

def SearchWay(l, s, m):

    n = len(l)

    # Initialize curr_sum as 
    # value of first element 
    # and starting point as 0 
    count = start = 0
    curr_sum = l[0]

    # Initialize the index as 1
    index = 1

    # Add elements one by  
    # one to curr_sum and  
    # if the index exceeds  
    # the m, then remove  
    # starting element
    # and change the value 
    # of index as m-1
    i = 1
    while i <= n:

        # If curr_sum becomes 
        # equal to sum, then 
        # increment count by 1
        if curr_sum == s and index == m:
            count += 1

        # If index exceeds 
        # the m, then remove 
        # the starting elements
        while index >= m:
            curr_sum -= l[start]
            start += 1
            index = m-1

        # Add this element  
        # to curr_sum and 
        # increment index
        if i < n:
            curr_sum += l[i]
            index += 1
        i += 1

    return count

# Driver's code
l = [1, 2, 1, 3, 2]
s = 3
m = 2

ans = SearchWay(l, s, m)
print(ans)
```

**输出:**

```
2

```

方法 2 的时间复杂度看起来不止 O(n)，但是如果我们仔细看看程序，那么就可以算出时间复杂度是 O(n)。我们可以通过计算最坏情况下对 arr[]的每个元素执行的操作数来证明这一点。对每个元素最多执行 2 次操作:(a)将元素添加到 curr_sum 中(b)从 curr_sum 中减去元素。所以运算次数的上限是 2n，也就是 O(n)。
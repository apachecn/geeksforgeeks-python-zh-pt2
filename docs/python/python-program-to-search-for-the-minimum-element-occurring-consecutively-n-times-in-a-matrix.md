# Python 程序搜索矩阵中连续出现 n 次的最小元素

> 原文:[https://www . geesforgeks . org/python-程序-搜索矩阵中连续出现 n 次的最小元素/](https://www.geeksforgeeks.org/python-program-to-search-for-the-minimum-element-occurring-consecutively-n-times-in-a-matrix/)

给定一个包含 n 行的矩阵。每行有相同数量的 m 个元素。任务是找到矩阵中水平、垂直、对角连续 n 次出现的元素。如果有多个这样的元素，则打印最小的元素。如果没有这样的元素
，则打印-1。
**举例:**

```
Input : n = 4
 mat[5][5]  2 1 3 4 5
            3 2 1 3 4
            5 3 2 1 4
            5 4 3 2 1
            5 4 4 3 2
Output :  1

Input : n = 2 
 mat[4][4]  2 0 5 1
            0 5 3 5 
            8 4 1 1
            3 8 5 2
Output : 0
```

**实施:**

## 蟒蛇 3

```
def check(l,row,col ,n,l2):

    # Iterate through the matrix.
    # Check for diagonal.
    for i in range(row - n+1):
        for j in range(col - n+1):

            # Store the value in a temporary
            # variable.
            num = l[i][j]

            # Check for the condition only
            # if we have more rows and columns
            # than n.
            if(row-i >= n and col-j >= n):
                count = 0

                # check if the number is present
                # n times.
                for k in range(n):

                    # if number is not present n
                    # times than break
                    if(num != l[i+k][j+k]):
                        break

                    # increment the count for checking
                    # the condition follows.
                    else:
                        count += 1

                # if count is same or greater as that of
                # n than the number follows the condition.
                if(count == n):
                    l2.append(num)
            else:
                break

    #check for row condition
    for i in range(row):
        for j in range(col - (n-1) ):

            num = l[i][j]
            count = 0

            for k in range(n):

                if num != l[i][j + k]:
                    break
                else:
                    count+=1

            # if count is same or greater as that
            # of n than the number follows the condition.
            if(count==n):
                l2.append(num)

    #check for column condition.
    for i in range(row - (n-1)):
        for j in range(col):

            num = l[i][j]
            count = 0

            for k in range(n):

                if num != l[i+k][j]:
                    break
                else:
                    count += 1

            # if count is same or greater as that of
            # n than the number follows the condition.
            if(count == n):
                l2.append(num)

    # It would require a complex code to
    # check for anti-diagonal Just rotate
    # the matrix and check for diagonal
    # condition again.

    #matrix rotation by 90 degrees.
    for i in range(0, int(row / 2)):

        for j in range(i, col - i - 1):

            # store current cell in
            # num variable
            num = l[i][j]

            # move values from right to top
            l[i][j] = l[j][col - 1 - i]

            # move values from bottom to right
            l[j][col - 1 - i] = l[row - 1 - i][col - 1 - j]

            # move values from left to bottom
            l[row - 1 - i][col - 1 - j] = l[row - 1 - j][i]

            # assign num to left
            l[row - 1 - j][i] = num

    # Iterate through the rotated matrix.
    for i in range(row - n+1):
        for j in range(col - n+1):

            # Store the value in a
            # temprory variable.
            num = l[i][j]

            # Check for the condition only if
            # we have more rows and columns than n.
            if(row-i >= n and col-j >= n):
                count = 0

                # check if the number is present
                # n times.
                for k in range(n):

                    # if number is not present n
                    # times than break
                    if(num != l[i+k][j+k]):
                        break

                    # increment the count for checking
                    # the condition follows.
                    else:
                        count += 1

                # if count is same or greater as that of
                # n than the number follows the condition.
                if(count == n):
                    l2.append(num)
            else:
                break

    # check if any element followed the condition.
    if(len(l2) == 0):
        print(-1)

    # print the minimum of all the elements
    # which follow the condition.
    else:
        print(min(l2))

if __name__ == "__main__":

    # Create Matrix
    l = [[2, 1, 3, 4, 5],
        [0, 2, 1, 3, 4],
        [5, 0, 2, 1, 4],
        [5, 4, 0, 2, 1],
        [5, 4, 4, 0, 2]]

    # Create a list to store all the elements
    # which follow the condition.
    l2 = []
    check(l,4,4,2,l2)
```

**输出:**

```
0 
```
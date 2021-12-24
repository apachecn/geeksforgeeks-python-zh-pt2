# 寻找矩阵中下一个最近元素的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-find-下一个最近的矩阵元素/](https://www.geeksforgeeks.org/python-program-to-find-the-next-nearest-element-in-a-matrix/)

给定一个矩阵、一组坐标和一个元素，任务是编写一个 python 程序，它可以获得元素下一次出现的坐标。

> **输入:** test_list = [[4，3，1，2，3]，[7，5，3，6，3]，[8，5，3，5，3]，[1，2，3，4，6]]，I，j = 1，3，K = 3
> 
> **输出:** (1，4)
> 
> **说明:**在(1，3)之后，在(1，4)处找到 3
> 
> **输入:** test_list = [[4，3，1，2，3]，[7，5，3，6，3]，[8，5，3，5，3]，[1，2，3，4，6]]，I，j = 2，3，K = 3
> 
> **输出:** (2，4)
> 
> **说明:**在(2，3)之后，在(2，4)处找到 3

**方法:** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*枚举()*](https://www.geeksforgeeks.org/enumerate-in-python/)

在这种情况下，我们从所需的坐标开始迭代，并检查从行+ 1，列+ 1 到 N，N 坐标形成的矩形内的下一个最近的 K。如果找不到匹配项，则返回-1，-1。

**示例:**

## 蟒蛇 3

```
# get Nearest coord.
def near_coord(test_list, x, y, val):
    for idx, row in enumerate(test_list[x:]):
        for j, ele in enumerate(row):

            # checking for value at lower formed rectangle
            if ele == val and j > y:
                return idx + x, j

    # if no index found
    return -1, -1

# initializing list
test_list = [[4, 3, 1, 2, 3], [7, 5, 3, 6, 3],
             [8, 5, 3, 5, 3], [1, 2, 3, 4, 6]]

# printing original list
print("The original list is : " + str(test_list))

# initializing check coord
i, j = 1, 3

# initializing K
K = 3

# getting nearest coordinates
res_abs, res_ord = near_coord(test_list, i, j, K)

# printing result
print("Found K index : " + str((res_abs, res_ord)))
```

**输出:**

> 原来的名单是:[[4，3，1，2，3]，[7，5，3，6，3]，[8，5，3，5，3]，[1，2，3，4，6]]
> 
> 找到 K 指数:(1，4)
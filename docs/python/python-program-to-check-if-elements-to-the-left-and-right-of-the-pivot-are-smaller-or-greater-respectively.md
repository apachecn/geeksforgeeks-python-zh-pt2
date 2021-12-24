# Python 程序，检查枢轴左侧和右侧的元素是更小还是更大

> 原文:[https://www . geesforgeks . org/python-program-to-check-元素到枢轴的左边和右边是更小还是更大-分别/](https://www.geeksforgeeks.org/python-program-to-check-if-elements-to-the-left-and-right-of-the-pivot-are-smaller-or-greater-respectively/)

给定一个列表和一个索引，任务是编写一个 Python 程序，首先选择该索引处的元素作为轴心元素，然后测试元素是右边大还是左边小。

**示例:**

> **输入:** test_list = [4，3，5，6，9，16，11，10，12]，K = 4
> 
> **输出:**真
> 
> **说明:**Kth 指数的元素为 9，之前的元素较小，之后的元素较大。
> 
> **输入:** test_list = [4，3，5，6，9，16，11，10，1]，K = 4
> 
> **输出:**假
> 
> **说明:**Kth 指数的元素为 9，之前的元素较小但 1 在第 4 指数之后，小于 9。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*枚举()*](https://www.geeksforgeeks.org/enumerate-in-python/#:~:text=Enumerate()%20method%20adds%20a,tuples%20using%20list()%20method.)

在这种情况下，我们使用循环迭代元素，枚举用于获取索引，并检查索引是否大于或小于 K，以切换测试条件。

**程序:**

## 蟒蛇 3

```
# initializing list
test_list = [4, 3, 5, 6, 9, 16, 11, 10, 12]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 4

res = True
for idx, ele in enumerate(test_list):

    # checking for required conditions
    if (idx > K and ele < test_list[K]) or (idx < K and ele > test_list[K]):
        res = False

# printing result
print("Is condition met ? : " + str(res))
```

**输出:**

> 原来的名单是:[4，3，5，6，9，16，11，10，12]
> 
> 条件满足了吗？:真

**方法二:** *使用* [*all()*](https://www.geeksforgeeks.org/any-all-in-python/) *和* [*枚举()*](https://www.geeksforgeeks.org/enumerate-in-python/#:~:text=Enumerate()%20method%20adds%20a,tuples%20using%20list()%20method.)

使用 all()执行类似的任务，它可以使用单行生成器表达式测试所需的条件，以提供更紧凑的解决方案。

**程序:**

## 蟒蛇 3

```
# initializing list
test_list = [4, 3, 5, 6, 9, 16, 11, 10, 12]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 4

# all() used to check for condition using one liner
res = all(not ((idx > K and ele < test_list[K]) or (
    idx < K and ele > test_list[K])) for idx, ele in enumerate(test_list))

# printing result
print("Is condition met ? : " + str(res))
```

**输出:**

> 原来的名单是:[4，3，5，6，9，16，11，10，12]
> 
> 条件满足了吗？:真
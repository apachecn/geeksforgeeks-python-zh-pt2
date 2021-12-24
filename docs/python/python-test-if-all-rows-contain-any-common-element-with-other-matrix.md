# Python–测试所有行是否包含与其他矩阵相同的元素

> 原文:[https://www . geesforgeks . org/python-test-如果所有行都包含任何与其他元素共有的元素-matrix/](https://www.geeksforgeeks.org/python-test-if-all-rows-contain-any-common-element-with-other-matrix/)

给定两个矩阵，检查所有行是否包含至少一个与其他矩阵的相同索引行相同的元素。

> **输入** : test_list1 = [[5，6，1]，[2，4]，[9，3，5]]，test_list2 = [[9，1，2]，[9，8，2]，[3，7，10]]
> **输出**:真
> **说明** : 1，2，3 为行内常用元素。
> 
> **输入** : test_list1 = [[5，6，1]，[2，4]，[9，2，6]]，test_list2 = [[9，1，2]，[9，8，2]，[3，7，6]]
> **输出**:真
> **说明** : 1，2，6 为行内常用元素。

**方法#1:在运算符**中使用循环+

在这种情况下，我们迭代矩阵的每一行，并使用 In 运算符检查其他列表中的任何元素匹配，如果找到任何元素，我们将其标记为真，如果所有行都为真，则返回真。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Test if all rows contain any common element with other Matrix
# Using loop "+" in operator

# initializing lists
test_list1 = [[5, 6, 1], [2, 4], [9, 3, 5]]
test_list2 = [[9, 1, 2], [9, 8, 2], [3, 7, 10]]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

res = True
for idx in range(0, len(test_list1)):

    temp = False

    # checking for any common element in 2nd list
    for ele in test_list1[idx]:
        if ele in test_list2[idx]:
            temp = True
            break

    # if any element not found, Result is false   
    if not temp :
        res = False
        break

# printing result
print("All row contain common elements with other Matrix : " + str(res))
```

**输出:**

```py
The original list 1 is : [[5, 6, 1], [2, 4], [9, 3, 5]]
The original list 2 is : [[9, 1, 2], [9, 8, 2], [3, 7, 10]]
All row contain common elements with other Matrix : True
```

**方法 2:使用任意()+循环**

在这种情况下，避免了一个嵌套循环，并使用 any()计算结果，以获得第二个矩阵中的任何公共元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Test if all rows contain any common element with other Matrix
# Using loop any() "+" loop

# initializing lists
test_list1 = [[5, 6, 1], [2, 4], [9, 3, 5]]
test_list2 = [[9, 1, 2], [9, 8, 2], [3, 7, 10]]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

res = True
for idx in range(0, len(test_list1)):

    # checking for common element in list 2 in same index
    temp = any(ele in test_list2[idx] for ele in test_list1[idx])

    # if any element not found, Result is false   
    if not temp :
        res = False
        break

# printing result
print("All row contain common elements with other Matrix : " + str(res))
```

**输出:**

```py
The original list 1 is : [[5, 6, 1], [2, 4], [9, 3, 5]]
The original list 2 is : [[9, 1, 2], [9, 8, 2], [3, 7, 10]]
All row contain common elements with other Matrix : True
```
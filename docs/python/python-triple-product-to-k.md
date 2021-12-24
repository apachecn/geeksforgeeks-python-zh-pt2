# Python |三重积到 K

> 原文:[https://www.geeksforgeeks.org/python-triple-product-to-k/](https://www.geeksforgeeks.org/python-triple-product-to-k/)

获得导致特定解的对的乘积数的问题已经被讨论过很多次了，本文旨在将它扩展到 3 个数，并讨论解决这个特定问题的几种方法。让我们讨论一下实现这一点的某些方法。

**方法#1:使用嵌套循环**
这是一种简单的方法，可以解决这个特定的问题，并使用外部循环来迭代每个元素，内部循环检查将对乘以结果的剩余差异。

```
# Python3 code to demonstrate
# 3 element product
# using nested loops

# initializing list
test_list = [4, 1, 3, 2, 6, 12]

# initializing product
product = 24

# printing original list
print("The original list : " + str(test_list))

# using nested loops
# 3 element product
res = []
for i in range(0, len(test_list)-2):
    for j in range(i + 1, len(test_list)-1):
        for k in range(j + 1, len(test_list)):
            if test_list[i] * test_list[j] * test_list[k] == product:
                temp = []
                temp.append(test_list[i])
                temp.append(test_list[j])
                temp.append(test_list[k])
                res.append(tuple(temp))

# print result
print("The 3 product element list is : " + str(res))
```

**Output :**

```
The original list : [4, 1, 3, 2, 6, 12]
The 3 product element list is : [(4, 1, 6), (4, 3, 2), (1, 2, 12)]

```
# Python |有效范围产品

> 原文:[https://www.geeksforgeeks.org/python-valid-ranges-product/](https://www.geeksforgeeks.org/python-valid-ranges-product/)

很多时候，我们需要得到的不是整个列表的产品，而是它的一部分，并且是定期的。这些间隔有时是在遍历之前静态决定的，但有时，约束是更动态的，因此我们需要以更复杂的方式处理它。这里讨论的标准是非零组的乘积。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用循环**
这个任务可以使用循环使用蛮力的方式来执行。我们只是遍历列表中的每个元素，测试它的后续元素是否为非零值，一旦找到下一个为零的值，就执行乘积运算，并将其附加到结果列表中。

```py
# Python3 code to demonstrate
# Valid Ranges Product
# Using loops

# initializing list
test_list = [4, 9, 0, 0, 3, 4, 5, 0, 0, 4, 0]

# printing original list
print("The original list : " + str(test_list))

# using loops
# Valid Ranges Product
res = []
val = 1
for ele in test_list:
    if ele == 0:
        if val != 1:
            res.append(val)
            val = 1
    else:
        val *= ele

# print result
print("The non-zero group product of list is : " + str(res))
```

**Output :**

```py
The original list : [4, 9, 0, 0, 3, 4, 5, 0, 0, 4, 0]
The non-zero group product of list is : [36, 60, 4]

```
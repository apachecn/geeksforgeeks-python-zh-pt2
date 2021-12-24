# 测试列表中非邻居的 Python 程序

> 原文:[https://www . geesforgeks . org/python-非列表中邻居的测试程序/](https://www.geeksforgeeks.org/python-program-to-test-for-non-neighbours-in-list/)

给定 teo 元素，编写一个 Python 程序来检查它们不会作为列表中的邻居出现

**示例:**

> **输入** : test_list = [3，7，2，1，4，5，7，9]，I，j = 7，4
> **输出** : True
> **解释**:没有发生的 7 是 4 的邻居。
> 
> **输入** : test_list = [3，7，2，1，4，5，7，9]，I，j = 5，4
> **输出** : False
> **解释** : 5 发生的是 4 的邻居。

**方法#1:使用循环**

在这种情况下，我们在迭代列表时检查下一个和上一个元素是否不是 I 或 j。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test for Non-neighbours in List
# Using loop

# initializing list
test_list = [3, 7, 2, 1, 4, 5, 7, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing i, j
i, j = 7, 4

res = True
for idx in range(1, len(test_list) - 1):
    if test_list[idx] == i:

        # check for surrounding element to be j if i
        if test_list[idx - 1] == j or test_list[idx + 1] == j:
            res = False
            break

# printing result
print("Are i, j Non-neighbours' : " + str(res))
```

**Output**

```
The original list is : [3, 7, 2, 1, 4, 5, 7, 9]
Are i, j Non-neighbours' : True
```

**方法 2:使用** [**全部()**](https://www.geeksforgeeks.org/any-all-in-python/)

这是解决这个问题的一种线性方法。在本文中，我们使用 all()中生成器表达式中的 all()来执行检查所有元素的邻居的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test for Non-neighbours in List
# Using all()

# initializing list
test_list = [3, 7, 2, 1, 4, 5, 7, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing i, j
i, j = 7, 4

# checking for preceding and succeeding element 
# not to be j if curr is i
res = all(test_list[idx - 1] != j and test_list[idx + 1] !=
          j for idx in range(1, len(test_list) - 1) if test_list[idx] == i)

# printing result
print("Are i, j Non-neighbours' : " + str(res))
```

**Output**

```
The original list is : [3, 7, 2, 1, 4, 5, 7, 9]
Are i, j Non-neighbours' : True
```
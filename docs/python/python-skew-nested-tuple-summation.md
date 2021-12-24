# Python–倾斜嵌套元组求和

> 原文:[https://www . geesforgeks . org/python-skew-nested-tuple-summary/](https://www.geeksforgeeks.org/python-skew-nested-tuple-summation/)

给定一个元组，在第二个位置嵌套，返回第一个元素的总和。

> **输入** : test_tup = (5，(6，(1，(9，无)))
> **输出** : 21
> **解释** : 9 + 6 + 5 + 1 = 21。
> 
> **输入** : test_tup = (5，(6，(1，无))
> **输出** : 12
> **解释** : 1 + 6 + 5 = 12。

**方法#1:使用无限循环**

在这种情况下，我们在使用无限循环求和时执行进入偏斜结构，当我们达到无值时中断。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Skew Nested Tuple Summation
# Using infinite loop

# initializing tuple
test_tup = (5, (6, (1, (9, (10, None)))))

# printing original tuple
print("The original tuple is : " + str(test_tup))

res = 0
while test_tup:
    res += test_tup[0]

    # assigning inner tuple as original
    test_tup = test_tup[1]

# printing result 
print("Summation of 1st positions : " + str(res)) 
```

**Output**

```
The original tuple is : (5, (6, (1, (9, (10, None)))))
Summation of 1st positions : 31

```

**方法 2:使用递归**

在这种情况下，我们对元组的第二个元素执行求和和递归，返回 None。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Skew Nested Tuple Summation
# Using recursion

# helper function to perform task
def tup_sum(test_tup):

    # return on None 
    if not test_tup:
        return 0
    else:
        return test_tup[0] + tup_sum(test_tup[1])

# initializing tuple
test_tup = (5, (6, (1, (9, (10, None)))))

# printing original tuple
print("The original tuple is : " + str(test_tup))

# calling fnc.
res = tup_sum(test_tup)

# printing result 
print("Summation of 1st positions : " + str(res)) 
```

**Output**

```
The original tuple is : (5, (6, (1, (9, (10, None)))))
Summation of 1st positions : 31

```
# Python–求和元素匹配条件

> 原文:[https://www . geesforgeks . org/python-sum-elements-matching-condition/](https://www.geeksforgeeks.org/python-sum-elements-matching-condition/)

按条件检查数字/元素是一个人面临的常见问题，几乎在每个程序中都要做。有时我们还需要得到与特定条件相匹配的总和，以区分哪些不匹配，以便进一步利用。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用循环**
这是执行这个特殊任务的蛮力方法。在这种情况下，我们迭代列表，找到符合特定条件的元素并取和。

## 蟒蛇 3

```
# Python 3 code to demonstrate 
# Sum elements matching condition
# using loop

# initializing list
test_list = [3, 5, 1, 6, 7, 9]

# printing original list
print ("The original list is : " + str(test_list))

# using loop
# Sum elements matching condition
# checks for odd
res = 0
for ele in test_list:
    if ele % 2 != 0:
        res = res + ele 

# printing result
print ("The sum of odd elements: " + str(res))
```

**Output : **

```
The original list is : [3, 5, 1, 6, 7, 9]
The sum of odd elements: 25
```

**方法#2:使用 sum() +生成器表达式**
每当生成器表达式返回 true 时，该方法都会使用向 sum 添加元素的技巧。当列表用完时，返回符合条件的数字的总和。

## 蟒蛇 3

```
# Python 3 code to demonstrate 
# Sum elements matching condition
# using sum() + generator expression

# initializing list
test_list = [3, 5, 1, 6, 7, 9]

# printing original list
print ("The original list is : " + str(test_list))

# using sum() + generator expression
# Sum elements matching condition
# checks for odd
res = sum(i for i in test_list if i % 2 != 0)

# printing result
print ("The sum of odd elements: " + str(res))
```

**Output : **

```
The original list is : [3, 5, 1, 6, 7, 9]
The sum of odd elements: 25
```
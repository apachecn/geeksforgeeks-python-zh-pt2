# Python |异构列表中整数的求和

> 原文:[https://www . geesforgeks . org/python-异构列表中整数求和/](https://www.geeksforgeeks.org/python-summation-of-integers-in-heterogeneous-list/)

有时候，在使用 Python 时，我们会遇到一个问题，我们需要找到列表的总和。这个问题比较容易解决。但是如果我们有混合的数据类型，这可能会变得复杂。让我们讨论执行这项任务的某些方法。

**方法#1:使用类型铸造+异常处理**
我们可以使用蛮力方法来键入种姓每个元素，并在出现异常时捕捉异常。这可以确保只有整数被加到和，因此可以解决这个问题。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Summation of integers in heterogeneous list
# using type caste and exception handling

# initializing list
test_list = [5, 6, "gfg", 8, (5, 7), 'is', 9]

# printing original list
print("The original list is : " + str(test_list))

# Summation of integers in heterogeneous list
# using type caste and exception handling
res = 0
for ele in test_list:
    try:
        res += int(ele)
    except :
        pass

# printing result 
print("Summation of integers in list : " + str(res))
```

**Output : **

```
The original list is : [5, 6, 'gfg', 8, (5, 7), 'is', 9]
Summation of integers in list : 28
```

**方法 2:使用 sum() + isinstance()**
这个问题也可以使用 sum()的内置函数来解决，并且它还支持使用 isinstance()的实例过滤器，该过滤器可以被馈送整数，从而解决问题。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Summation of integers in heterogeneous list
# using sum() + isinstance()

# initializing list
test_list = [5, 6, "gfg", 8, (5, 7), 'is', 9]

# printing original list
print("The original list is : " + str(test_list))

# Summation of integers in heterogeneous list
# using sum() + isinstance()
res = sum(filter(lambda i: isinstance(i, int), test_list))

# printing result 
print("Summation of integers in list : " + str(res))
```

**Output : **

```
The original list is : [5, 6, 'gfg', 8, (5, 7), 'is', 9]
Summation of integers in list : 28
```
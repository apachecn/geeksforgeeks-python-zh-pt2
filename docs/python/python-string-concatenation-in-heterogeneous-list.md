# Python–异构列表中的字符串串联

> 原文:[https://www . geesforgeks . org/python-string-concation-in-异类-list/](https://www.geeksforgeeks.org/python-string-concatenation-in-heterogeneous-list/)

有时候，在使用 Python 时，我们会遇到一个问题，我们需要找到字符串的连接。这个问题比较容易解决。但是如果我们有混合的数据类型，这可能会变得复杂。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+条件**
我们可以使用蛮力方法来键入种姓检查每个元素，如果它是一个字符串，我们将它连接起来。这可以确保只有字符串被连接，因此可以解决这个问题。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# String concatenation in Heterogeneous list
# using loop + conditions

# initializing list
test_list = [5, 6, "gfg ", 8, (5, 7), ' is', 9, ' best']

# printing original list
print("The original list is : " + str(test_list))

# String concatenation in Heterogeneous list
# using loop + conditions
res = ''
for ele in test_list:
    if type(ele) == str:
        res += ele 

# printing result 
print("Concatenation of strings in list : " + str(res))
```

**Output : **

```py
The original list is : [5, 6, 'gfg ', 8, (5, 7), ' is', 9, ' best']
Concatenation of strings in list : gfg  is best
```

**方法 2:使用 join() + isinstance()**
这个问题也可以通过使用 join()的内置函数来解决，它还支持使用 isinstance()的实例过滤器，该过滤器可以用字符串进行馈送，从而解决问题。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# String concatenation in Heterogeneous list
# using join() + isinstance()

# initializing list
test_list = [5, 6, "gfg ", 8, (5, 7), ' is', 9, ' best']

# printing original list
print("The original list is : " + str(test_list))

# String concatenation in Heterogeneous list
# using join() + isinstance()
res = "".join(filter(lambda i: isinstance(i, str), test_list))

# printing result 
print("Concatenation of strings in list : " + str(res))
```

**Output : **

```py
The original list is : [5, 6, 'gfg ', 8, (5, 7), ' is', 9, ' best']
Concatenation of strings in list : gfg  is best
```
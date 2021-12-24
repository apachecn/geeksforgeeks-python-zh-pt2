# Python 中连接两个列表的方法

> 原文:[https://www . geesforgeks . org/python-连接两个列表的方法/](https://www.geeksforgeeks.org/python-ways-to-concatenate-two-lists/)

让我们看看如何在 Python 中使用不同的方法连接两个列表。当我们有许多需要以类似方式处理的元素列表时，此操作非常有用。

**方法#1 :** 使用朴素方法

在这个方法中，我们遍历第二个列表，并继续在第一个列表中追加元素，这样第一个列表将拥有两个列表中的所有元素，因此将执行追加。

```
# Python3 code to demonstrate list
# concatenation using naive method 

# Initializing lists
test_list1 = [1, 4, 5, 6, 5]
test_list2 = [3, 5, 7, 2, 5]

# using naive method to concat
for i in test_list2 :
    test_list1.append(i)

# Printing concatenated list
print ("Concatenated list using naive method : " 
                              + str(test_list1))
```

**Output:**

```
Concatenated list using naive method : [1, 4, 5, 6, 5, 3, 5, 7, 2, 5]

```

**方法 2 :** 使用+运算符

执行列表连接的最传统的方法是使用“+”运算符，它可以轻松地将一个列表的整体添加到另一个列表的后面，从而执行连接。

```
# Python 3 code to demonstrate list
# concatenation using + operator 

# Initializing lists
test_list3 = [1, 4, 5, 6, 5]
test_list4 = [3, 5, 7, 2, 5]

# using + operator to concat
test_list3 = test_list3 + test_list4

# Printing concatenated list
print ("Concatenated list using + : "
                   + str(test_list3))
```

**Output:**

```
Concatenated list using + : [1, 4, 5, 6, 5, 3, 5, 7, 2, 5]

```

**方法 3 :** 使用列表理解

列表理解也可以完成这个列表连接的任务。在这种情况下，会创建一个新的列表，但是这个方法是上面讨论的循环方法的一个线性替代方法。

```
# Python3 code to demonstrate list
# concatenation using list comprehension 

# Initializing lists
test_list1 = [1, 4, 5, 6, 5]
test_list2 = [3, 5, 7, 2, 5]

# using list comprehension to concat
res_list = [y for x in [test_list1, test_list2] for y in x]

# Printing concatenated list
print ("Concatenated list using list comprehension: "
                                     + str(res_list))
```

**Output:**

```
Concatenated list using list comprehension: [1, 4, 5, 6, 5, 3, 5, 7, 2, 5]

```
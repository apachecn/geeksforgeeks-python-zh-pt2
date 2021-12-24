# Python 成员和身份操作符

> 原文:[https://www . geesforgeks . org/python-成员资格-身份-操作员-非-非/](https://www.geeksforgeeks.org/python-membership-identity-operators-not-not/)

在本文中，我们将讨论 Python 成员资格和身份运算符。

## **会员运营商**

成员资格运算符是用于验证值的成员资格的运算符。它测试序列中的成员资格，如字符串、列表或元组。

*   **In operator:** T1】 in operator is used to check whether there is a value in the sequence. If a variable in the specified sequence is found, it is evaluated as true; otherwise, it is evaluated as false.

## 蟒 3

```
# Python program to illustrate
# Finding common member in list
# using 'in' operator
list1=[1,2,3,4,5]
list2=[6,7,8,9]
for item in list1:
    if item in list2:
        print("overlapping")     
else:
    print("not overlapping")
```
# Python–测试列表

中是否存在任何集合元素

> 原文:[https://www . geesforgeks . org/python-test-if-set-element-exists-in-list/](https://www.geeksforgeeks.org/python-test-if-any-set-element-exists-in-list/)

给定一个集合和列表，任务是编写一个 python 程序来检查列表中是否存在任何集合元素。

**示例:**

> **输入:** test_dict1 = test_set = {6，4，2，7，9，1}，test_list = [6，8，10]
> 
> **输出:**真
> 
> **说明:** 6 出现在集合列表中。
> 
> **输入:** test_dict1 = test_set = {16，4，2，7，9，1}，test_list = [6，8，10]
> 
> **输出:**假
> 
> **说明:**列表中不存在集合元素。

**方法#1:使用** [**任意()**](https://www.geeksforgeeks.org/python-any-function/)

在这种情况下，我们迭代集合的所有元素，并检查列表中是否出现任何元素。对于任何元素匹配条件， *any()* 返回真。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if any set element exists in List
# Using any()

# initializing set
test_set = {6, 4, 2, 7, 9, 1}

# printing original set
print("The original set is : " + str(test_set))

# initializing list
test_list = [6, 8, 10]

# any() checking for any set element in check list
res = any(ele in test_set for ele in test_list)

# printing result
print("Any set element is in list ? : " + str(res))
```

**输出:**

```
The original set is : {1, 2, 4, 6, 7, 9}
Any set element is in list ? : True
```

**方法 2:使用** [**&运算符**](https://www.geeksforgeeks.org/python-bitwise-operators/)

在这种情况下，我们通过在集合和列表之间使用 and 操作来检查任何元素，如果有任何元素匹配，结果为真。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if any set element exists in List
# Using & operator

# initializing set
test_set = {6, 4, 2, 7, 9, 1}

# printing original set
print("The original set is : " + str(test_set))

# initializing list
test_list = [6, 8, 10]

# & operator checks for any common element
res = bool(test_set & set(test_list))

# printing result
print("Any set element is in list ? : " + str(res))
```

**输出:**

```
The original set is : {1, 2, 4, 6, 7, 9}
Any set element is in list ? : True
```
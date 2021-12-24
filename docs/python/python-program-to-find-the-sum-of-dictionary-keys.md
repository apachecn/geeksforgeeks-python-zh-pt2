# Python 程序查找字典键之和

> 原文:[https://www . geesforgeks . org/python-program-to-find-sum-of-dictionary-key/](https://www.geeksforgeeks.org/python-program-to-find-the-sum-of-dictionary-keys/)

给定一个带有整数键的字典。任务是找出所有键的总和。

**例:**

```
Input : test_dict = {3 : 4, 9 : 10, 15 : 10, 5 : 7} 
Output : 32 
Explanation : 3 + 9 + 15 + 5 = 32, sum of keys.

Input : test_dict = {3 : 4, 9 : 10, 15 : 10} 
Output : 27 
Explanation : 3 + 9 + 15 = 27, sum of keys. 
```

**方法#1:使用循环**

这是执行这项任务的方法之一。在这种情况下，我们迭代字典中的所有关键字，并使用计数器计算总和。

T3】蟒 3T5

```
# Python3 code to demonstrate working of
# Dictionary Keys Summation
# Using loop

# initializing dictionary
test_dict = {3: 4, 9: 10, 15: 10, 5: 7, 6: 7}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

res = 0
for key in test_dict:

    # adding keys
    res += key

# printing result
print("The dictionary keys summation : " + str(res))
```

T6T8**输出**T1

**方法 2:使用键()+ sum()**

这是一种速记，在它的帮助下可以完成这项任务。在本例中，我们使用[键()](https://www.geeksforgeeks.org/python-dictionary-keys-method/)提取列表中的所有键，并使用[求和()](https://www.geeksforgeeks.org/sum-function-python/)执行求和。

## python 3

```
# Python3 code to demonstrate working of
# Dictionary Keys Summation
# Using keys() + sum()

# initializing dictionary
test_dict = {3: 4, 9: 10, 15: 10, 5: 7, 6: 7}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# sum() performs summation
res = sum(list(test_dict.keys()))

# printing result
print("The dictionary keys summation : " + str(res))
```

**输出**

```
The original dictionary is : {3: 4, 9: 10, 15: 10, 5: 7, 6: 7}
The dictionary keys summation : 38

```
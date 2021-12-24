# Python–字典中自定义嵌套键的总和

> 原文:[https://www . geeksforgeeks . org/python-自定义嵌套键总和-in-dictionary/](https://www.geeksforgeeks.org/python-summation-of-custom-nested-keys-in-dictionary/)

给定关键字为嵌套字典的字典，求嵌套字典中某些自定义关键字的值之和。

> **输入** : test_dict = {'Gfg' : {1 : 6，5: 9，9: 12}，' is' : {1 : 9，5: 7，9: 2}，' best' : {1 : 3，5: 4，9: 14}}，sum_key = [1]
> **输出** : 18
> **解释** : 6 + 9 + 3 = 18，只对带 key 1 的值求和。
> 
> **输入** : test_dict = {'Gfg' : {1 : 6，5: 9，9: 12}，' is' : {1 : 9，5: 7，9: 2}，' best' : {1 : 3，5: 4，9: 14}}，sum_key = [5，9]
> **输出** : 48
> **解释**:按键 5，9 相加。

**方法#1:循环**

这是解决这个问题的粗暴方法。在这种情况下，我们对所有列表元素使用一个循环，并不断更新所有嵌套字典的和值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Summation of Custom nested keys in Dictionary
# Using loop

# initializing dictionary
test_dict = {'Gfg' : {1 : 6, 5: 9, 9: 12},
             'is' : {1 : 9, 5: 7, 9: 2}, 
             'best' : {1 : 3, 5: 4, 9: 14}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing sum keys 
sum_key = [1, 9]

sum = 0
for ele in sum_key:
    for key, val in test_dict.items():

        # extracting summation of required values
        sum = sum + val[ele]

# printing result 
print("The required summation : " + str(sum)) 
```

**Output**

> 原字典为:{'Gfg': {1: 6，5: 9，9: 12}，' is': {1: 9，5: 7，9: 2}，' best': {1: 3，5: 4，9: 14}}
> 所需求和:46

**方法 2:使用列表理解+求和()**

上述功能的组合也可以用来解决这个问题。在这种情况下，我们使用 sum()执行求和任务，其余逻辑也使用列表理解封装为一行。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Summation of Custom nested keys in Dictionary
# Using list comprehension + sum()

# initializing dictionary
test_dict = {'Gfg' : {1 : 6, 5: 9, 9: 12},
             'is' : {1 : 9, 5: 7, 9: 2}, 
             'best' : {1 : 3, 5: 4, 9: 14}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing sum keys 
sum_key = [1, 9]

# sum() used to get cumulative summation
res = sum([val[ele] for ele in sum_key for key, val in test_dict.items()])

# printing result 
print("The required summation : " + str(res)) 
```

**Output**

> 原字典为:{'Gfg': {1: 6，5: 9，9: 12}，' is': {1: 9，5: 7，9: 2}，' best': {1: 3，5: 4，9: 14}}
> 所需求和:46
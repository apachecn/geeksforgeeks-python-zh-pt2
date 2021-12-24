# Python–字典列表所有值总和

> 原文:[https://www . geesforgeks . org/python-字典列表-所有值-求和/](https://www.geeksforgeeks.org/python-list-of-dictionaries-all-values-summation/)

给定一个字典列表，提取所有值的总和。

> **输入** : test_list = [{“苹果”:2、“芒果”:2、“葡萄”:2}、{“苹果”:2、“芒果”:2、“葡萄”:2}]
> **输出** : 12
> **解释**:2+2+……(6-次)= 12，所有值之和。
> 
> **输入** : test_list = [{“苹果”:3、“芒果”:2、“葡萄”:2}、{“苹果”:2、“芒果”:3、“葡萄”:3}]
> **输出** : 15
> **解释**:所有数值相加得出 15。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，我们对列表中的所有字典进行迭代，然后对每个字典的所有键进行求和。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# List of dictionaries all values Summation
# Using loop

# initializing lists
test_list = [{"Gfg" : 6, "is" : 9, "best" : 10}, 
             {"Gfg" : 8, "is" : 11, "best" : 19},
             {"Gfg" : 2, "is" : 16, "best" : 10},
             {"Gfg" : 12, "is" : 1, "best" : 8},
             {"Gfg" : 22, "is" : 6, "best" : 8}]

# printing original list
print("The original list : " + str(test_list))

res = 0
# loop for dictionaries
for sub in test_list:
    for key in sub:

        # summation of each key 
        res += sub[key]

# printing result 
print("The computed sum : " + str(res))
```

**Output**

```py
The original list : [{'Gfg': 6, 'is': 9, 'best': 10}, {'Gfg': 8, 'is': 11, 'best': 19}, {'Gfg': 2, 'is': 16, 'best': 10}, {'Gfg': 12, 'is': 1, 'best': 8}, {'Gfg': 22, 'is': 6, 'best': 8}]
The computed sum : 148

```

**方法 2:使用 sum() + values() +列表理解**

上述功能的组合可以作为解决这个问题的一个线性替代方案。在这种情况下，使用 sum()执行求和，values()用于提取列表中所有字典的值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# List of dictionaries all values Summation
# Using sum() + values() + list comprehension

# initializing lists
test_list = [{"Gfg" : 6, "is" : 9, "best" : 10}, 
             {"Gfg" : 8, "is" : 11, "best" : 19},
             {"Gfg" : 2, "is" : 16, "best" : 10},
             {"Gfg" : 12, "is" : 1, "best" : 8},
             {"Gfg" : 22, "is" : 6, "best" : 8}]

# printing original list
print("The original list : " + str(test_list))

res = sum([sum(list(sub.values())) for sub in test_list])

# printing result 
print("The computed sum : " + str(res))
```

**Output**

```py
The original list : [{'Gfg': 6, 'is': 9, 'best': 10}, {'Gfg': 8, 'is': 11, 'best': 19}, {'Gfg': 2, 'is': 16, 'best': 10}, {'Gfg': 12, 'is': 1, 'best': 8}, {'Gfg': 22, 'is': 6, 'best': 8}]
The computed sum : 148

```
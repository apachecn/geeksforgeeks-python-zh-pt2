# Python–将字典值四舍五入到 K 位小数

> 原文:[https://www . geesforgeks . org/python-round-off-dictionary-values-to-k-decimals/](https://www.geeksforgeeks.org/python-round-off-dictionary-values-to-k-decimals/)

给定带有浮点值的字典对所有值进行舍入。

> **输入**:{“Gfg”:54.684034，“is”:76.324334，“Best”:28.43524 }，K = 2
> **输出**:{“Gfg”:54.68，“is”:76.32，“Best”:28.43 }
> **解释**:数值四舍五入至 2。
> 
> **输入**:{“Gfg”:54.684034，“is”:76.324334，“Best”:28.43524 }，K = 1
> **输出**:{“Gfg”:54.6，“is”:76.3，“Best”:28.4 }
> **解释**:取整至 1 的值。

**方法#1:使用循环+ round()**

这是执行这项任务的方法之一。在本例中，我们对所有值进行迭代，并使用 round()执行舍入到最近的 K 值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Round Off Dictionary Values to K decimals
# Using loop + round()

# initializing dictionary
test_dict = {"Gfg" : 54.684034, "is" : 76.324334, "Best" : 28.43524}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 3

# loop to iterate for values 
res = dict()
for key in test_dict:

    # rounding to K using round()
    res[key] = round(test_dict[key], K)

# printing result 
print("Values after round off : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 54.684034, 'is': 76.324334, 'Best': 28.43524}
Values after round off : {'Gfg': 54.684, 'is': 76.324, 'Best': 28.435}

```

**方法 2:使用词典理解+ round()**

这是执行这项任务的另一种方式。在本文中，我们使用上述功能执行了类似的任务，不同之处在于使用字典理解来提供单行解决方案。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Round Off Dictionary Values to K decimals
# Using dictionary comprehension + round()

# initializing dictionary
test_dict = {"Gfg" : 54.684034, "is" : 76.324334, "Best" : 28.43524}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 3

# Encapsulating solution using single comprehension
res = {key : round(test_dict[key], K) for key in test_dict}

# printing result 
print("Values after round off : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 54.684034, 'is': 76.324334, 'Best': 28.43524}
Values after round off : {'Gfg': 54.684, 'is': 76.324, 'Best': 28.435}

```
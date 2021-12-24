# Python–解析字典中的浮动键

> 原文:[https://www . geesforgeks . org/python-resolve-float-key-in-dictionary/](https://www.geeksforgeeks.org/python-resolve-float-keys-in-dictionary/)

给定一个包含多种浮点键的字典，找到一种以单值形式访问它们的方法。

> **输入**:test _ dict = {“010.78”:“Gfg”、“9.0”:“is”、“10”:“Best”}，K =“09.0”
> **输出**:“is”
> **解释** : 09.0 - > 9.0 其值为“is”。
> 
> **输入**:test _ dict = {“010.78”:“Gfg”、“9.0”:“is”、“10”:“Best”}，K =“10.0”
> **输出**:“Best”
> **解释** : 10.0 - > 10 其值为“Best”。

**方法#1:使用 float() + loop**

这是解决这个问题的方法之一。在这种情况下，使用的策略是使用 float()将键转换为浮点值，它解析为单个值，并在转换为 float()后执行输入字符串的检查，两者都解析为公共浮点值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Resolve Float Keys in Dictionary
# Using float() + loop()

# initializing dictionary
test_dict = {"010.78" : "Gfg", "9.0" : "is", "10" : "Best"}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = "10.78"

# performing resolution
res = dict()
for key in test_dict:
    res[float(key)] = test_dict[key]

# converting compare value to float 
convK = float(K)

# performing value access 
res = res[convK]

# printing result 
print("Value of resolved float Key : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'010.78': 'Gfg', '9.0': 'is', '10': 'Best'}
Value of resolved float Key : Gfg

```

**方法 2:使用词典理解+ float()**

这种计算方式与上述方法类似。不同的是转换使用了一个线性字典理解。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Resolve Float Keys in Dictionary
# Using dictionary comprehension + float()

# initializing dictionary
test_dict = {"010.78" : "Gfg", "9.0" : "is", "10" : "Best"}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = "10.78"

# performing resolution using dictionary comprehension
res = {float(key) : test_dict[key] for key in test_dict}

# converting compare value to float 
convK = float(K)

# performing value access 
res = res[convK]

# printing result 
print("Value of resolved float Key : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'010.78': 'Gfg', '9.0': 'is', '10': 'Best'}
Value of resolved float Key : Gfg

```
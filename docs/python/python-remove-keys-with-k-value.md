# Python–移除 K 值的键

> 原文:[https://www . geesforgeks . org/python-remove-key-with-k-value/](https://www.geeksforgeeks.org/python-remove-keys-with-k-value/)

给定一个字典，移除所有值等于 k 的键

> **输入** : test_dict = {'Gfg' : 8，' is' : 7，' best' : 8，' for' : 6，' geeks' : 11}，K = 8
> **输出** : {'is' : 7，' for' : 6，' geeks' : 11}
> **解释**:“Gfg”和“best”，取值 8，均去掉。
> 
> **输入** : test_dict = {'Gfg' : 8，' is' : 8，' best' : 8，' for' : 8，' geeks' : 8}，K = 8
> **输出** : {}
> **解释**:值为 8 的所有键都被移除。

**方法一:利用词典理解**

这是执行这项任务的方法之一。在这种情况下，我们只检查不等于 K 的元素并保留它，在字典理解中作为一行。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove Keys with K value
# Using dictionary comprehension

# initializing dictionary
test_dict = {'Gfg' : 6, 'is' : 7, 'best' : 9, 'for' : 6, 'geeks' : 11} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 6

# using dictionary comprehension 
# to compare not equal to K and retain 
res = {key: val for key, val in test_dict.items() if val != K}

# printing result 
print("The filtered dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 6, 'is': 7, 'best': 9, 'for': 6, 'geeks': 11}
The filtered dictionary : {'is': 7, 'best': 9, 'geeks': 11}

```

**方法 2:使用 dict() + filter() + lambda**

上述功能的组合可以用来解决这个问题。在这种情况下，我们过滤所有非 K 元素并保留。最后，使用 dict()将结果转换为字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove Keys with K value
# Using dict() + filter() + lambda

# initializing dictionary
test_dict = {'Gfg' : 6, 'is' : 7, 'best' : 9, 'for' : 6, 'geeks' : 11} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 6

# employing lambda for computation 
# filter() to perform filter according to lambda
res = dict(filter(lambda key: key[1] != K, test_dict.items()))

# printing result 
print("The filtered dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 6, 'is': 7, 'best': 9, 'for': 6, 'geeks': 11}
The filtered dictionary : {'is': 7, 'best': 9, 'geeks': 11}

```
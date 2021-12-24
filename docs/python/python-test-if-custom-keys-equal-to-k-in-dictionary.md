# Python–测试自定义键是否等于字典中的 K

> 原文:[https://www . geesforgeks . org/python-test-if-custom-key-等于字典中的 k/](https://www.geeksforgeeks.org/python-test-if-custom-keys-equal-to-k-in-dictionary/)

给定字典和自定义键列表，检查是否所有这些自定义键都等于 k

> **输入**:test _ dict = {“Gfg”:5、“is”:8、“Best”:10、“for”:10、“Geeks”:10 }、cust _ keys =[“is”、“for”、“Geeks”]，K = 10
> 
> **输出**:假
> 
> **解释**:“是”的值是 8 而不是 10，因此为假
> 
> **输入**:test _ dict = {“Gfg”:5、“is”:10、“Best”:10、“for”:10、“Geeks”:10 }、cust _ keys =[“is”、“for”、“Geeks”]，K = 10
> 
> **输出**:真
> 
> **说明**:所有键都有 10 作为值。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在本文中，我们迭代每个自定义键，并通过使用布尔变量跟踪来检查是否所有键都等于 K。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test if custom keys equal to K in dictionary
# Using loop

# initializing dictionary
test_dict = {"Gfg" : 5, "is" : 8, "Best" : 10, "for" : 8, "Geeks" : 8}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing custom keys list 
cust_keys = ["is", "for", "Geeks"]

# initializing K 
K = 8

# using loop to check for all keys 
res = True 
for key in cust_keys:
    if test_dict[key] != K:

        # break even if 1 value is not equal to K
        res = False 
        break

# printing result 
print("Are all custom keys equal to K : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 5, 'is': 8, 'Best': 10, 'for': 8, 'Geeks': 8}
Are all custom keys equal to K : True

```

**方法 2:使用 all() +生成器表达式**

上述功能的组合可以用来解决这个问题。在本例中，我们使用 all()检查所有值，生成器表达式执行所需的迭代。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test if custom keys equal to K in dictionary
# Using all() + generator expression

# initializing dictionary
test_dict = {"Gfg" : 5, "is" : 8, "Best" : 10, "for" : 8, "Geeks" : 8}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing custom keys list 
cust_keys = ["is", "for", "Geeks"]

# initializing K 
K = 8

# returns true if all elements match K  
res = all(test_dict[key] == K for key in cust_keys)

# printing result 
print("Are all custom keys equal to K : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 5, 'is': 8, 'Best': 10, 'for': 8, 'Geeks': 8}
Are all custom keys equal to K : True

```
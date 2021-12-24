# Python–删除值大于 K 的键(包括混合值)

> 原文:[https://www . geesforgeks . org/python-remove-key-with-values-大于-k-包括-混合值/](https://www.geeksforgeeks.org/python-remove-keys-with-values-greater-than-k-including-mixed-values/)

给定一个包含键值对的字典，移除所有值大于 K 的键，包括混合值。

> **输入** : test_dict = {'Gfg' : 3，' is' : 7，' best' : 10，' for' : 6，' geeks' : 'CS'}，K = 7
> **输出** : {'Gfg' : 3，' for' : 6，' geeks' : 'CS'}
> **解释**:所有大于 K 的值都被移除。混合值被保留。
> 
> **输入** : test_dict = {'Gfg' : 3，' is' : 7，' best' : 10，' for' : 6，' geeks' : 'CS'}，K = 1
> **输出** : {'geeks' : 'CS'}
> **解释**:只保留 Mixed 值。

**方法#1:使用 isinstance() +循环**

这是执行这项任务的方法之一。在这种情况下，我们使用实例来获取整数值，并通过比较来获取不大于 k 的值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove keys with Values Greater than K ( Including mixed values )
# Using loop + isinstance()

# initializing dictionary
test_dict = {'Gfg' : 3, 'is' : 7, 'best' : 10, 'for' : 6, 'geeks' : 'CS'} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 6

# using loop to iterate keys of dictionary
res = {}
for key in test_dict:

    # testing for data type and then condition, order is imp.
    if not (isinstance(test_dict[key], int) and test_dict[key] > K):
        res[key] = test_dict[key]

# printing result 
print("The constructed dictionary : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': 3, 'is': 7, 'best': 10, 'for': 6, 'geeks': 'CS'}
The constructed dictionary : {'Gfg': 3, 'for': 6, 'geeks': 'CS'}

```

**方法 2:使用词典理解+ isinstance()**

上述功能的组合用于解决这个问题。这执行类似于上述方法的任务。唯一不同的是，它使用字典理解在一行中执行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove keys with Values Greater than K ( Including mixed values )
# Using dictionary comprehension + isinstance()

# initializing dictionary
test_dict = {'Gfg' : 3, 'is' : 7, 'best' : 10, 'for' : 6, 'geeks' : 'CS'} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 6

# using list comprehension to perform in one line
res = {key : val for key, val in test_dict.items() if not (isinstance(val, int) and (val > K))}

# printing result 
print("The constructed dictionary : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': 3, 'is': 7, 'best': 10, 'for': 6, 'geeks': 'CS'}
The constructed dictionary : {'Gfg': 3, 'for': 6, 'geeks': 'CS'}

```
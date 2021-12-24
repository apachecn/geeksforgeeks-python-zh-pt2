# Python–从嵌套字典中移除 K 值键

> 原文:[https://www . geesforgeks . org/python-remove-k-value-key-from-nested-dictionary/](https://www.geeksforgeeks.org/python-remove-k-valued-key-from-nested-dictionary/)

有时，在处理记录时，我们可能会遇到一个问题，即我们需要从嵌套字典中移除一个键，该键的值特定于 k。这是一个常见的问题，它在数据领域(如 web 开发)中有其应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'CS': { '无价':6}、' is': {'better': 6}、' gfg': {'best': 6}}
> **输出**:{ ' CS ':}、' gfg': {}、' is': {}
> 
> **输入** : test_dict = {'CS': { '无价':9}、' is': {'better': 8}、' gfg': {'best': 7}}
> **输出** : {'CS': { '无价':9}、' is': {'better': 8}、' gfg': {'best': 7}}

**方法#1:使用 loop + isinstance() + `filter()`**
以上函数的组合可以用来解决这个问题。在本例中，我们使用 filter()执行 K 值任务，并使用 isinstance()测试嵌套字典。字典的构造是使用循环完成的。

```
# Python3 code to demonstrate working of 
# Remove K valued key from Nested Dictionary
# Using loop + isinstance() + filter()

# initializing dictionary
test_dict = {'gfg' : {'best' : 4, 'good' : 5}, 
             'is' : {'better' : 6, 'educational' : 4},
             'CS' : {'priceless' : 6}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing rem_val
rem_val = 6

# Remove K valued key from Nested Dictionary
# Using loop + isinstance() + filter()
def rem_vals(ele):
  global rem_val
  key, val = ele
  return val != rem_val

res = dict()
for key, val in test_dict.items():
  if isinstance(val, dict):
    res[key] = dict(filter(rem_vals, val.items()))
  else:
    res[key] = val

# printing result 
print("Dictionary after removal : " + str(res)) 
```

**Output :**

> 原词典:{'is': {'educational': 4，' better': 6}，' gfg': {'best': 4，' good': 5}，' CS': { '无价':6}}
> 删除后的词典:{'is': {'educational': 4}，' gfg': {'best': 4，' good': 5}，' CS': {}

**方法 2:使用字典理解+ `isinstance()` + lamda**
上述功能的组合可用于使用 lambda 函数在一行中执行该任务。

```
# Python3 code to demonstrate working of 
# Remove K valued key from Nested Dictionary
# Using dictionary comprehension + isinstance() + lamda

# initializing dictionary
test_dict = {'gfg' : {'best' : 4, 'good' : 5}, 
             'is' : {'better' : 6, 'educational' : 4},
             'CS' : {'priceless' : 6}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing rem_val
rem_val = 6

# Remove K valued key from Nested Dictionary
# Using dictionary comprehension + isinstance() + lamda
fnc = lambda sub: { key1: fnc(val1) if isinstance(val1, dict) else val1
      for key1, val1 in sub.items() if val1 != rem_val}
res = fnc(test_dict)

# printing result 
print("Dictionary after removal : " + str(res)) 
```

**Output :**

> 原词典:{'is': {'educational': 4，' better': 6}，' gfg': {'best': 4，' good': 5}，' CS': { '无价':6}}
> 删除后的词典:{'is': {'educational': 4}，' gfg': {'best': 4，' good': 5}，' CS': {}
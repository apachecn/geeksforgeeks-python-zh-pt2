# Python–根据关键字的索引值对字典列表进行排序

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-list-by-key-with-index-value/](https://www.geeksforgeeks.org/python-sort-dictionary-list-by-keys-ith-index-value/)

给定字典列表，根据关键字的索引值对字典进行排序

> **输入**:[{“Gfg”:“Best”，“for”:“Geeks”}，{“Gfg”:“Good”，“for”:“Me”}，{“Gfg”:“Better”，“for”:“All”}]，K =“Gfg”，i = 1
> **输出**:[{“Gfg”:“Best”，“for”:“Geeks”}，{“Gfg”:“Better”，“for”:“All”}，{“Gfg”:“Good”，“for”:“Me”
> 
> **输入**:[{“Gfg”:“Best”，“for”:“Geeks”}，{“Gfg”:“Good”，“for”:“Me”}，{“Gfg”:“Better”，“for”:“All”}]，K =“Gfg”，i = 0
> **输出**:[{“Gfg”:“Best”，“for”:“Geeks”}，{“Gfg”:“Better”，“for”:“All”}，{“Gfg”:“Good”，“for”:“Me”

**方法#1:使用 sort() + lambda**

上述功能的组合可以用来解决这个问题。在这种情况下，我们在“键”参数驱动条件下使用 sort()和 lambda 函数执行排序任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort Dictionary List by Key's ith Index value
# Using sort() + lambda

# initializing lists
test_list = [{"Gfg" : "Best", "for" : "Geeks"},
             {"Gfg" : "Good", "for" : "Me"},
             {"Gfg" : "Better", "for" : "All"}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = "Gfg"

# initializing i 
i = 2

# using sort to perform sort(), lambda
# function drives conditions
res = sorted(test_list, key = lambda sub: sub[K][i])

# printing result 
print("List after sorting : " + str(res))
```

**Output**

> 原列表:[{'Gfg': 'Best '，' for': 'Geeks'}，{'Gfg': 'Good '，' for': 'Me'}，{'Gfg': 'Better '，' for': 'All'}]
> 排序后的列表:[{'Gfg': 'Good '，' for': 'Me'}，{'Gfg': 'Best '，' for': 'Geeks'}，{'Gfg': 'Better '，' for': 'All'}]

**方法 2:使用 sort() + lambda + get()**

以上功能的结合也可以解决这个问题。这只是上述方法的一个微小变化。在这种情况下，我们使用 get()来避免键不出现在特定记录中的可能性。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort Dictionary List by Key's ith Index value
# Using sort() + lambda + get()

# initializing lists
test_list = [{"Gfg" : "Best", "for" : "Geeks"},
             {"Gfg" : "Good", "for" : "Me"},
             {"Gfg" : "Better", "for" : "All"}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = "Gfg"

# initializing i 
i = 2

# using sort to perform sort(), lambda
# function drives conditions, get() used to 
# avoid missing key error
res = sorted(test_list, key = lambda sub: sub.get(K)[i])

# printing result 
print("List after sorting : " + str(res))
```

**Output**

> 原列表:[{'Gfg': 'Best '，' for': 'Geeks'}，{'Gfg': 'Good '，' for': 'Me'}，{'Gfg': 'Better '，' for': 'All'}]
> 排序后的列表:[{'Gfg': 'Good '，' for': 'Me'}，{'Gfg': 'Best '，' for': 'Geeks'}，{'Gfg': 'Better '，' for': 'All'}]
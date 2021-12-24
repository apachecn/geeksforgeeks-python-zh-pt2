# Python |移除列表中的重复词典

> 原文:[https://www . geesforgeks . org/python-remove-replica-dicts-in-list/](https://www.geeksforgeeks.org/python-removing-duplicate-dicts-in-list/)

在许多应用中，消除重复是必不可少的。字典列表很常见，有时我们需要复制副本。让我们讨论实现这一目标的某些方法。

**方法#1:幼稚方法**
执行此操作时想到的基本方法是迭代字典列表并手动移除重复字典并追加到新列表中的幼稚方法。

```py
# Python3 code to demonstrate 
# remove duplicate dictionary
# using naive method 

# initializing list
test_list = [{"Akash" : 1}, {"Kil" : 2}, {"Akshat" : 3}, {"Kil" : 2}, {"Akshat" : 3}]

# printing original list 
print ("Original list : " + str(test_list))

# using naive method to 
# remove duplicates 
res_list = []
for i in range(len(test_list)):
    if test_list[i] not in test_list[i + 1:]:
        res_list.append(test_list[i])

# printing resultant list
print ("Resultant list is : " + str(res_list))
```

**输出:**

```py
Original list : [{'Akash': 1}, {'Kil': 2}, {'Akshat': 3}, {'Kil': 2}, {'Akshat': 3}]
Resultant list is : [{'Akash': 1}, {'Kil': 2}, {'Akshat': 3}]

```

**方法 2:使用列表理解**
使用列表理解和枚举可能允许在一行中完成这个特定的任务，因此具有很好的实用性。

```py
# Python3 code to demonstrate 
# remove duplicate dictionary
# using list comprehension

# initializing list
test_list = [{"Akash" : 1}, {"Kil" : 2}, {"Akshat" : 3}, {"Kil" : 2}, {"Akshat" : 3}]

# printing original list 
print ("Original list : " + str(test_list))

# using list comprehension to 
# remove duplicates 
res_list = [i for n, i in enumerate(test_list) if i not in test_list[n + 1:]]

# printing resultant list
print ("Resultant list is : " + str(res_list))
```

**输出:**

```py
Original list : [{'Akash': 1}, {'Kil': 2}, {'Akshat': 3}, {'Kil': 2}, {'Akshat': 3}]
Resultant list is : [{'Akash': 1}, {'Kil': 2}, {'Akshat': 3}]

```

**方法 3:使用 frozenset**
frozenset 用于将字典中的某个键赋值为一个集合。因此，字典中重复的条目被忽略，从而解决了这个特殊的任务。

```py
# Python3 code to demonstrate 
# remove duplicate dictionary
# using frozenset

# initializing list
test_list = [{"Akash" : 1}, {"Kil" : 2}, {"Akshat" : 3}, {"Kil" : 2}, {"Akshat" : 3}]

# printing original list 
print ("Original list : " + str(test_list))

# using frozenset to 
# remove duplicates 
res_list = {frozenset(item.items()) : item for item in test_list}.values()

# printing resultant list
print ("Resultant list is : " + str(res_list))
```

**输出:**

```py
Original list : [{'Akash': 1}, {'Kil': 2}, {'Akshat': 3}, {'Kil': 2}, {'Akshat': 3}]
Resultant list is : [{'Kil': 2}, {'Akshat': 3}, {'Akash': 1}]

```
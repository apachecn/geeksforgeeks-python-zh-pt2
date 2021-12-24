# Python |抄录字典键

> 原文:[https://www . geesforgeks . org/python-抄录-字典-键/](https://www.geeksforgeeks.org/python-transcribing-dictionary-key/)

在处理数据时，我们可以遇到我们希望执行的各种数据转换。这些可以是将字典列表中的一个关键字转录到外部进行概括。知道这种类型的实用程序非常有用。让我们讨论一下实现这一点的某些方法。

**方法一:利用词典理解**

这个特殊的任务可以使用字典理解的方法来完成，在这种方法中，我们从所需的列表中分配关键字和值，并重新构建字典。

```
# Python3 code to demonstrate
# Dictionary key transcription
# dictionary comprehension

# initializing list
test_list = [{'state' : 'Haryana', 'capital' : 'Chandigarh', 'area' : 'North'},
             {'state' : 'Karnataka', 'capital' : 'Bengaluru', 'area' : 'South'}]

# printing original list
print("The original list : " + str(test_list))

# using Dictionary comprehension
# Dictionary key transcription
res = { sub["state"]: {"capital": sub["capital"], "area": sub["area"] }
        for sub in test_list }

# print result
print("The Dictionary after transcription of key : " + str(res))
```

**Output :**

> 原列表:[{ '大写':'昌迪加尔'，'州':'哈里亚纳'，'地区':'北方' }，{ '大写':'孟加拉鲁'，'州':'卡纳塔克邦'，'地区':'南方' }]
> 
> 转录后的字典键:{ '哈里亚纳邦':{ '大写':'昌迪加尔'，'地区':'北方' }，'卡纳塔克邦':{ '大写':'孟加拉鲁'，'地区':'南方' }}

**方法二:利用字典理解+ `items() + get()`**

这个任务也可以使用一组函数来执行。这种方法允许灵活地添加任意选择的键。这在事先不知道密钥的情况下很有用。

```
# Python3 code to demonstrate
# Dictionary key transcription
# dictionary comprehension + items() + get()

# initializing list
test_list = [{'state' : 'Haryana', 'capital' : 'Chandigarh', 'area' : 'North'},
             {'state' : 'Karnataka', 'capital' : 'Bengaluru', 'area' : 'South'}]

# printing original list
print("The original list : " + str(test_list))

# using dictionary comprehension + items() + get()
# Dictionary key transcription
res = {sub.get('state'): {key: val for key, val in sub.items()
        if key != 'state'} for sub in test_list}

# print result
print("The Dictionary after transcription of key : " + str(res))
```

**Output :**

> 原列表:[{ '大写':'昌迪加尔'，'州':'哈里亚纳'，'地区':'北方' }，{ '大写':'孟加拉鲁'，'州':'卡纳塔克邦'，'地区':'南方' }]
> 
> 转录后的字典键:{ '哈里亚纳邦':{ '大写':'昌迪加尔'，'地区':'北方' }，'卡纳塔克邦':{ '大写':'孟加拉鲁'，'地区':'南方' }}
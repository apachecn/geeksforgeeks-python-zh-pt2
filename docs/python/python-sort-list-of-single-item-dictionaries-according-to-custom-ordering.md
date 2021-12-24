# Python–根据自定义排序对单项词典列表进行排序

> 原文:[https://www . geesforgeks . org/python-sort-单品列表-词典-按自定义排序/](https://www.geeksforgeeks.org/python-sort-list-of-single-item-dictionaries-according-to-custom-ordering/)

给定单品字典列表和关键字排序列表，根据自定义关键字执行字典排序。

> **输入** : test_list1 = [{'is' : 4}，{“Gfg”:10 }，{“Best”:1 }]，test _ list 2 =[“Gfg”，“is”，“Best”]
> **输出** : [{'Gfg': 10}，{'is' : 4}，{'Best': 1}]
> **解释**:通过列表排序，字典列表得到排序。
> 
> **输入**:test _ list 1 =[{“Gfg”:10 }，{“is”:4 }，{“Best”:1 }]，test _ list 2 =[“Gfg”，“is”，“Best”]
> **输出**:[{“Gfg”:10 }，{“is”:4 }，{“Best”:1 }]
> **说明**:已订购。不需要重新排序。

**方法#1:使用排序的()+索引()+键()+λ**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 sorted()执行排序，index()用于从自定义列表中获取排序，keys()用于从字典中提取关键字。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort list of Single Item dictionaries according to custom ordering
# Using sorted() + index() + keys() + lambda 

# initializing lists
test_list1 = [{'is' : 4}, {'for' : 7}, {"Gfg" : 10}, {"Best" : 1}, {"CS" : 8}] 
test_list2 = ["Gfg", "is", "Best", "for", "CS"]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# sorted() used to perform sort(), returns the result
# to other variable, ordering handled using index() from order list
res = sorted(test_list1, key = lambda ele: test_list2.index(list(ele.keys())[0]))

# printing result 
print("The custom order list : " + str(res)) 
```

**Output**

> 原始列表 1 为:[{'is': 4}、{'for': 7}、{'Gfg': 10}、{'Best': 1}、{'CS': 8}]
> 原始列表 2 为:['Gfg '、' is '、' Best '、' for '、' CS']
> 自定义顺序列表:[{'Gfg': 10}、{'is': 4}、{'Best': 1}、{'for': 7}、{'CS': 8}]

**方法 2:使用 sort()+index()+key()+lambda**

这是执行这项任务的另一种方式。在本例中，我们使用 sort()执行排序任务，执行就地排序，其他构造保持不变。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort list of Single Item dictionaries according to custom ordering
# Using sort() + index() + keys() + lambda

# initializing lists
test_list1 = [{'is' : 4}, {'for' : 7}, {"Gfg" : 10}, {"Best" : 1}, {"CS" : 8}] 
test_list2 = ["Gfg", "is", "Best", "for", "CS"]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# sort() used to perform inplace sort
test_list1.sort(key = lambda ele: test_list2.index(list(ele.keys())[0]))

# printing result 
print("The custom order list : " + str(test_list1)) 
```

**Output**

> 原始列表 1 为:[{'is': 4}、{'for': 7}、{'Gfg': 10}、{'Best': 1}、{'CS': 8}]
> 原始列表 2 为:['Gfg '、' is '、' Best '、' for '、' CS']
> 自定义顺序列表:[{'Gfg': 10}、{'is': 4}、{'Best': 1}、{'for': 7}、{'CS': 8}]
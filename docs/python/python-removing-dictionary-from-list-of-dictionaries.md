# Python |从词典列表中删除词典

> 原文:[https://www . geesforgeks . org/python-从词典列表中删除词典/](https://www.geeksforgeeks.org/python-removing-dictionary-from-list-of-dictionaries/)

删除字典列表中特定关键字对应的字典的常用工具也是一个问题，它的简明版本总是有帮助的。由于引入了非 SQL 数据库，这在 web 开发中有应用，非 SQL 数据库主要在键值对上工作。让我们讨论执行这项任务的某些方法。

**方法#1:使用 del + loop**
在执行这个特定任务的天真方法中，我们要求使用 *del* 来删除特定的密钥，如果它与需要删除的密钥匹配的话。

```
# Python3 code to demonstrate 
# to delete dictionary in list
# using del + loop 

# initializing list of dictionaries
test_list = [{"id" : 1, "data" : "HappY"},
             {"id" : 2, "data" : "BirthDaY"},
             {"id" : 3, "data" : "Rash"}]

# printing original list 
print ("The original list is : " + str(test_list))

# using del + loop 
# to delete dictionary in list
for i in range(len(test_list)):
    if test_list[i]['id'] == 2:
        del test_list[i]
        break

# printing result
print ("List after deletion of dictionary : " +  str(test_list))
```

**Output:**

> 原始列表为:[{'id': 1，' data': 'HappY'}，{'id': 2，' data ':' PoLicy ' }，{'id': 3，' data': 'Rash'}]
> 删除字典后的列表:[{'id': 1，' data': 'HappY'}，{'id': 3，' data': 'Rash'}]
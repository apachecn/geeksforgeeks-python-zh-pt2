# Python |按日期给定字典列表排序

> 原文:[https://www . geesforgeks . org/python-sort-given-list-按日期排列的词典/](https://www.geeksforgeeks.org/python-sort-given-list-of-dictionaries-by-date/)

给定一个字典列表，任务是按日期对字典进行排序。让我们看几个解决任务的方法。

**方法#1:使用天真的方法**

```
# Python code to demonstrate
# sort a list of dictionary
# where value date is in string

# Initialising list of dictionary
ini_list = [{'name':'akash', 'd.o.b':'1997-03-02'},
            {'name':'manjeet', 'd.o.b':'1997-01-04'}, 
            {'name':'nikhil', 'd.o.b':'1997-09-13'}]

# printing initial list
print ("initial list : ", str(ini_list))

# code to sort list on date
ini_list.sort(key = lambda x:x['d.o.b'])

# printing final list
print ("result", str(ini_list))
```

**输出:**

> 初始列表:[{'name': 'akash '，' d.o.b': '1997-03-02'}，{'name': 'manjeet '，' d.o.b': '1997-01-04'}，{'name': 'nikhil '，' d.o.b': '1997-09-13'}]
> 
> 结果[{'name': 'manjeet '，' d.o.b': '1997-01-04'}，{'name': 'akash '，' d.o.b': '1997-03-02'}，{'name': 'nikhil '，' d.o.b': '1997-09-13'}]
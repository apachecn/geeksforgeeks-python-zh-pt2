# Python 程序提取唯一字典值列表元素

> 原文:[https://www . geesforgeks . org/python-程序-提取-唯一-字典-值-列表-元素/](https://www.geeksforgeeks.org/python-program-to-extract-the-unique-dictionary-value-list-elements/)

给定带有值列表的字典，提取所有唯一值。

> **输入** : test_dict = {"Gfg" : [6，7，4，6]，"极客":[6，8，5，2]}
> **输出** : [6，7，4，8，5，2]
> **解释**:提取所有区分元素。
> 
> **输入**:test _ dict = {“Gfg”:[6，7，6]，“极客”:[6，8，5，2]}
> **输出** : [6，7，8，5，2]
> **解释**:提取所有区分元素。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，当元素出现时，我们会记住它们，并防止它们重新进入结果列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Unique Dictionary Value List elements
# Using loop

# initializing dictionary
test_dict = {"Gfg" : [6, 7, 4, 6], 
             "is" : [8, 9, 5], 
             "for" : [2, 5, 3, 7], 
             "Geeks" : [6, 8, 5, 2]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# list to memorize elements and insert result
res = []
for sub in test_dict:
    for ele in test_dict[sub]:

        # testing for existence
        if ele not in res:
            res.append(ele)

# printing result 
print("Extracted items : " + str(res)) 
```

**输出:**

> 原词典为:{'Gfg': [6，7，4，6]，' is': [8，9，5]，' for': [2，5，3，7]，' Geeks': [6，8，5，2]}
> 
> 提取的项目:[6、7、4、8、9、5、2、3]

**方法 2:使用** [**集()**](https://www.geeksforgeeks.org/python-set-method/) **+** [**联()**](https://www.geeksforgeeks.org/union-function-python/)

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 set()转换所有列表，然后跨所有键执行所有元素的并集，以获得所需的结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Unique Dictionary Value List elements
# Using set() + union()

# initializing dictionary
test_dict = {"Gfg" : [6, 7, 4, 6], 
             "is" : [8, 9, 5], 
             "for" : [2, 5, 3, 7], 
             "Geeks" : [6, 8, 5, 2]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using * operator to get union 
res = list(set().union(*test_dict.values()))

# printing result 
print("Extracted items : " + str(res)) 
```

**输出:**

> 原词典为:{'Gfg': [6，7，4，6]，' is': [8，9，5]，' for': [2，5，3，7]，' Geeks': [6，8，5，2]}
> 
> 提取的项目:[6，7，4，8，9，5，2，3
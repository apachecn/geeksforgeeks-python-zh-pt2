# Python–偶数值测试字典值列表

> 原文:[https://www . geesforgeks . org/python-测试偶数值-字典-值-列表/](https://www.geeksforgeeks.org/python-test-for-even-values-dictionary-values-lists/)

给定一个以列表为值的字典，根据列表中的所有值映射布尔值是否为偶数。

> **输入**:{“Gfg”:[6，8，10]，“is”:[8，10，12，16]，“Best”:[10，16，14，6]}
> **输出**:{‘Gfg’:True，‘is’:True，‘Best’:True }
> **:所有列表均为偶数。**
> 
> ****输入**:{“Gfg”:[6，5，10]，“is”:[8，10，11，16]，“Best”:[10，16，14，6]}
> **输出**:{‘Gfg’:False，‘is’:False，‘Best’:True }
> **:只有“Best”有偶数。****

******方法#1:使用循环******

****这是执行这项任务的粗暴方式。在这种情况下，我们对所有值进行迭代，并检查是否所有列表值都是。即使是，我们也将键指定为“真”或“假”。****

## ****蟒蛇 3****

```py
**# Python3 code to demonstrate working of 
# Test for Even values dictionary values lists
# Using loop

# initializing dictionary
test_dict = {"Gfg" : [6, 7, 3], 
             "is" :  [8, 10, 12, 16], 
             "Best" : [10, 16, 14, 6]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

res = dict()
for sub in test_dict:
    flag = 1

    # checking for even elements
    for ele in test_dict[sub]:
        if ele % 2 != 0:
            flag = 0
            break
    # adding True if all Even elements
    res[sub] = True if flag else False

# printing result 
print("The computed dictionary : " + str(res)) **
```

******Output**

```py
The original dictionary is : {'Gfg': [6, 7, 3], 'is': [8, 10, 12, 16], 'Best': [10, 16, 14, 6]}
The computed dictionary : {'Gfg': False, 'is': True, 'Best': True}

```**** 

******方法二:使用 all() +词典理解******

****这是执行这项任务的另一种方式。在这种情况下，我们使用 all()检查所有元素，并使用字典理解来重新生成结果。****

## ****蟒蛇 3****

```py
**# Python3 code to demonstrate working of 
# Test for Even values dictionary values lists
# Using all() + dictionary comprehension

# initializing dictionary
test_dict = {"Gfg" : [6, 7, 3], 
             "is" :  [8, 10, 12, 16], 
             "Best" : [10, 16, 14, 6]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using all to check for all even elements
res = {sub : all(ele % 2 == 0 for ele in test_dict[sub]) for sub in test_dict}

# printing result 
print("The computed dictionary : " + str(res)) **
```

******Output**

```py
The original dictionary is : {'Gfg': [6, 7, 3], 'is': [8, 10, 12, 16], 'Best': [10, 16, 14, 6]}
The computed dictionary : {'Gfg': False, 'is': True, 'Best': True}

```****
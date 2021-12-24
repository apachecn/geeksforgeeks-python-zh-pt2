# Python–从其他字典中替换字典值

> 原文:[https://www . geesforgeks . org/python-replace-dictionary-value-from-other-dictionary/](https://www.geeksforgeeks.org/python-replace-dictionary-value-from-other-dictionary/)

给定两个字典，如果键存在于另一个字典中，则更新来自另一个字典的值。

> **输入**:test _ dict = {“Gfg”:5、“is”:8、“Best”:10、“for”:8、“极客”:9}、
> updict = {“极客”:10、“Best”:17 }
> **输出**:{“Gfg”:5、“is”:8、“Best”:17、“for”:8、“极客”:10}
> **解释**:“极客”和“Best”值更新为 10 和 17。
> 
> **输入**:test _ dict = {“Gfg”:5、“is”:8、“Best”:10、“for”:8、“极客”:9}、
> updict = {“极客”:10、“Bet”:17 }
> **输出**:{“Gfg”:5、“is”:8、“Best”:10、“for”:8、“极客”:9}
> **解释**:无值匹配，故原词典。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，我们为目标字典中的每个键运行一个循环，并在该值出现在其他字典中的情况下进行更新。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Replace dictionary value from other dictionary
# Using loop

# initializing dictionary
test_dict = {"Gfg" : 5, "is" : 8, "Best" : 10, "for" : 8, "Geeks" : 9}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing updict
updict = {"Gfg"  : 10, "Best" : 17}

for sub in test_dict:

    # checking if key present in other dictionary
    if sub in updict:
        test_dict[sub]  = updict[sub]

# printing result 
print("The updated dictionary: " + str(test_dict)) 
```

**Output**

> 原版词典是:{'Gfg': 5，' is': 8，' Best': 10，' for': 8，' Geeks': 9}
> 更新后的词典:{'Gfg': 10，' is': 8，' Best': 17，' for': 8，' Geeks': 9}

**方法二:利用词典理解**

这是一种可以执行该任务的线性方法。在这种情况下，我们迭代所有的字典值，并在字典理解中以一行的方式更新。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Replace dictionary value from other dictionary
# Using dictionary comprehension

# initializing dictionary
test_dict = {"Gfg" : 5, "is" : 8, "Best" : 10, "for" : 8, "Geeks" : 9}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing updict
updict = {"Gfg"  : 10, "Best" : 17}

res = {key: updict.get(key, test_dict[key]) for key in test_dict}

# printing result 
print("The updated dictionary: " + str(res)) 
```

**Output**

> 原版词典是:{'Gfg': 5，' is': 8，' Best': 10，' for': 8，' Geeks': 9}
> 更新后的词典:{'Gfg': 10，' is': 8，' Best': 17，' for': 8，' Geeks': 9}
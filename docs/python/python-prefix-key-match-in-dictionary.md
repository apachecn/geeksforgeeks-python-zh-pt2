# Python |字典中前缀键匹配

> 原文:[https://www . geesforgeks . org/python-prefix-key-match-in-dictionary/](https://www.geeksforgeeks.org/python-prefix-key-match-in-dictionary/)

有时，在使用字典时，我们可能会遇到一个问题，即我们需要找到对键有一些约束的字典项。一个这样的约束可以是关键字上的前缀匹配。让我们讨论执行这项任务的某些方法。

**方法#1:使用字典理解+ `startswith()`**
以上两种方法的结合可以用来执行这个特定的任务。在这种情况下，词典理解完成词典构建的基本任务，`startswith()`执行从特定前缀开始检查关键字的实用任务。

```
# Python3 code to demonstrate working of
# Prefix key match in dictionary
# Using dictionary comprehension + startswith()

# Initialize dictionary
test_dict = {'tough' : 1, 'to' : 2, 'do' : 3, 'todays' : 4, 'work' : 5}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Initialize prefix 
test_pref = 'to'

# Using dictionary comprehension + startswith()
# Prefix key match in dictionary
res = {key:val for key, val in test_dict.items() 
                   if key.startswith(test_pref)}

# printing result 
print("Filtered dictionary keys are : " + str(res))
```

**Output :**

> 原始字典:{'to': 2，'强硬':1，'工作':5，'今日':4，' do': 3}
> 筛选的字典键为:{'to': 2，'强硬':1，'今日':4}
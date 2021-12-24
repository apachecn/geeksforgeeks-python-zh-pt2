# Python–替换字符串中的重复出现

> 原文:[https://www . geesforgeks . org/python-replace-replice-in-occurrence-in-string/](https://www.geeksforgeeks.org/python-replace-duplicate-occurrence-in-string/)

有时，在使用 Python 字符串时，我们可能会遇到需要执行单词替换的问题。这是相当常见的任务，已经讨论过很多次了。但有时，要求仅替换重复的出现，即从第二次出现开始。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`split() + enumerate()` +循环**
上述功能的组合可用于执行该任务。在这种情况下，我们使用拆分来分隔单词。在这种情况下，我们记住 set 中的第一次出现，并检查该值是否在已经出现之前保存，然后被替换。

```
# Python3 code to demonstrate working of 
# Replace duplicate Occurrence in String
# Using split() + enumerate() + loop

# initializing string
test_str = 'Gfg is best . Gfg also has Classes now. \
                Classes help understand better . '

# printing original string
print("The original string is : " + str(test_str))

# initializing replace mapping 
repl_dict = {'Gfg' :  'It', 'Classes' : 'They' }

# Replace duplicate Occurrence in String
# Using split() + enumerate() + loop
test_list = test_str.split(' ')
res = set()
for idx, ele in enumerate(test_list):
    if ele in repl_dict:
        if ele in res:
            test_list[idx] = repl_dict[ele]
        else:
            res.add(ele)
res = ' '.join(test_list)

# printing result 
print("The string after replacing : " + str(res)) 
```

**Output :**

> 原来的字符串是:Gfg 最好。Gfg 现在也有课程了。课程有助于更好地理解。
> 替换后的字符串:Gfg 最好。现在也有课了。它们有助于更好地理解。
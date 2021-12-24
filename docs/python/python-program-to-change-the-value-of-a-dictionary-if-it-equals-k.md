# Python 程序改变字典的值，如果它等于 K

> 原文:[https://www . geesforgeks . org/python-program-to-change-value-of-a-dictionary-if-it-equals-k/](https://www.geeksforgeeks.org/python-program-to-change-the-value-of-a-dictionary-if-it-equals-k/)

给定一个字典，如果它等于 k，则更改该值。

> **输入**:test _ dict = {“Gfg”:4、“is”:8、“best”:10、“for”:8、“极客”:19}、K = 8、repl_val = 25
> **输出**:{“Gfg”:4、“is”:25、“best”:10、“for”:25、“极客”:19}
> **解释**:所有带 8 的值转换为 25。
> 
> **输入**:test _ dict = {“Gfg”:6、“is”:8、“best”:10、“for”:8、“极客”:19}、K = 6、repl_val = 25
> **输出**:{“Gfg”:25、“is”:8、“best”:10、“for”:8、“极客”:19}
> **解释**:所有带 6 的值转换为 25。

**方法#1:使用**一个**循环**

这是执行这项任务的一种粗暴方式。在这种情况下，我们迭代字典的所有键和值，如果发现匹配，则执行所需的转换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Change value if value equals K in dictionary
# Using loop

# initializing dictionary
test_dict = {"Gfg": 4, "is": 8, "best": 10, "for": 8, "geeks": 19}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K  
K = 8

# initializing repl_val 
repl_val = 20

# iterating dictionary
for key, val in test_dict.items():

    # checking for required value
    if val == K:
        test_dict[key] = repl_val

# printing result 
print("The dictionary after values replacement : " + str(test_dict))
```

**Output**

> 原词典为:{'Gfg': 4，' is': 8，' best': 10，' for': 8，' geeks': 19}
> 值替换后的词典:{'Gfg': 4，' is': 20，' best': 10，' for': 20，' geeks': 19}

**方法二:利用词典理解**

这是一个解决这个问题的单行替代方案。在这种情况下，我们迭代并分配创建一个新的字典，而不是像上面的方法那样进行就地替换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Change value if value equals K in dictionary
# Using dictionary comprehension

# initializing dictionary
test_dict = {"Gfg": 4, "is": 8, "best": 10, "for": 8, "geeks": 19}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K  
K = 8

# initializing repl_val 
repl_val = 20

# one-liner to solve for dictionary
res = {key : repl_val if val == K else val for key, val in test_dict.items()}

# printing result 
print("The dictionary after values replacement : " + str(res))
```

**Output**

> 原词典为:{'Gfg': 4，' is': 8，' best': 10，' for': 8，' geeks': 19}
> 值替换后的词典:{'Gfg': 4，' is': 20，' best': 10，' for': 20，' geeks': 19}
# Python–从字典中删除 Kth 键

> 原文:[https://www . geesforgeks . org/python-remove-kth-key-from-dictionary/](https://www.geeksforgeeks.org/python-remove-kth-key-from-dictionary/)

很多时候，在使用 Python 时，我们可能会遇到这样的情况:我们需要移除字典的第 k 个键。这对于 Python 版本很有用，在该版本中，键的顺序类似于插入顺序。让我们讨论执行这项任务的某些方法。

**例:**

> **输入**:test _ dict = {“Gfg”:20、“is”:36、“best”:100、“for”:17、“极客”:1}、K = 4
> **输出**:{“Gfg”:20、“is”:36、“best”:100、“极客”:1}
> **解释**:第 4 个索引，for 被移除。
> 
> **输入**:test _ dict = {“Gfg”:20、“is”:36、“best”:100、“for”:17、“极客”:1}、K = 2
> **输出**:{“Gfg”:20、“best”:100、“for”:17、“极客”:1}
> **解释**:第 2 个索引，“is”被移除。

**方法#1:使用 del +循环**

这是执行这项任务的方法之一。在这种情况下，我们迭代键和计数器，当我们得到键时，我们执行它的移除。这将执行就地移除。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove Kth key from dictionary
# Using loop

# initializing dictionary
test_dict = {"Gfg" : 20, "is" : 36, "best" : 100,
             "for" : 17, "geeks" : 1} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing size 
K = 3

cnt = 0
for key in test_dict:
    cnt += 1

    # delete key if counter is equal to K
    if cnt == K:
        del test_dict[key]
        break

# printing result 
print("Required dictionary after removal : " + str(test_dict)) 
```

**输出:**

> 原词典为:{'Gfg': 20，' is': 36，' best': 100，' for': 17，'极客':1}
> 删除后的必备词典:{'Gfg': 20，' is': 36，' for': 17，'极客':1}

**方法二:使用按键()+字典理解**

这是执行这项任务的另一种方式。在这种情况下，我们在不包含所需密钥的情况下重新创建字典，通过使用 key()提取要移除的密钥，我们将除必需密钥之外的所有密钥都包含到新字典中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove Kth key from dictionary
# Using Remove Kth key from dictionary

# initializing dictionary
test_dict = {"Gfg" : 20, "is" : 36, "best" : 100,
             "for" : 17, "geeks" : 1} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing size 
K = 3

# dictionary comprehension remakes dictionary, 
# rather than removing
res = {key: val for key, val in test_dict.items() 
       if key != list(test_dict.keys())[K - 1]}

# printing result 
print("Required dictionary after removal : " + str(res))
```

**输出:**

> 原词典为:{'Gfg': 20，' is': 36，' best': 100，' for': 17，'极客':1}
> 删除后的必备词典:{'Gfg': 20，' is': 36，' for': 17，'极客':1}
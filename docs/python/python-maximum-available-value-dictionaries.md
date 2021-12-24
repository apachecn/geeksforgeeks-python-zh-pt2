# Python–最大可用值词典

> 原文:[https://www . geesforgeks . org/python-最大可用值-字典/](https://www.geeksforgeeks.org/python-maximum-available-value-dictionaries/)

给定字典列表和一个列表，从列表中提取包含最大可用键值的所有字典。

> **输入**:test _ list[{“Gfg”:6，“is”:9，“best”:10 }，
> {“Gfg”:8，“is”:11，“best”:19 }，
> {“Gfg”:2，“is”:16，“best”:10 }]，K =“best”，arg_list = [10，7，6，12]
> **输出**:[{“Gfg”:6，“is”:9，“best”:10 }，{“Gfg”:0 为 10，则返回所有对应的词典。
> 
> **输入**:test _ list[{“Gfg”:6，“is”:9，“best”:10 }，
> {“Gfg”:8，“is”:11，“best”:19 }]，K =“Gfg”，arg_list = [10，7，6，12]
> **输出**:[{“Gfg”:6，“is”:9，“best”:10 }]
> **:本例中出现的最大值为 6，因此返回。**

**方法#1:使用循环**

这是解决这个问题的粗暴方法。在这种情况下，第一个最大值是从字典值中获得的，它也存在于提供的列表中。发布所有具有该值的字典都已提取。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Maximum available value Dictionaries
# Using loop

# initializing lists
test_list = [{"Gfg" : 6, "is" : 9, "best" : 10}, 
             {"Gfg" : 8, "is" : 11, "best" : 19},
             {"Gfg" : 2, "is" : 16, "best" : 10},
             {"Gfg" : 12, "is" : 1, "best" : 8},
             {"Gfg" : 22, "is" : 6, "best" : 8}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = "best"

# initializing list 
arg_list = [10, 7, 6, 12]

# extracting value to find from dictionary
# corresponding to key 
max_ele = 0
for sub in test_list:
    if sub[K] in arg_list:

        # maximum of all possible present for a key
        max_ele = max(sub[K], max_ele)

# extracting dictionary with maximum and present value of key 
res = [sub for sub in test_list if sub[K] == max_ele]

# printing result 
print("The extracted dictionaries : " + str(res))
```

**Output**

> 原始列表:[{'Gfg': 6，' is': 9，' best': 10}，{'Gfg': 8，' is': 11，' best': 19}，{'Gfg': 2，' is': 16，' best': 10}，{'Gfg': 12，' is': 1，' best': 8}，{'Gfg': 22 '，is': 6，' best': 8}]
> 提取的字典:[{'Gfg': 6，' is': 9，' best': 10}，{'Gfg': 2，' is ':
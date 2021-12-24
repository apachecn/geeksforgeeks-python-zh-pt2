# Python–字符串列表中单词的开始和结束索引

> 原文:[https://www . geesforgeks . org/python-从字符串列表开始和结束单词索引/](https://www.geeksforgeeks.org/python-start-and-end-indices-of-words-from-list-in-string/)

给定一个字符串，我们的任务是编写一个 Python 程序，从一个字符串中提取另一个列表的单词的所有元素的开始和结束索引。

> **输入:**test _ str =“gfg 最适合所有 CS 极客和工程求职者”，check_list = [“极客”、“工程”、“最佳”、“gfg”]
> 
> **输出:** { '极客':[23，27]，'工程':[33，43]，'最佳':[7，10]，' gfg': [0，2]}
> 
> **说明:**“极客”从索引号 23 开始，一直到 27，结果如此。
> 
> **输入:**test _ str =“gfg 最适合所有 CS 极客和工程求职者”，check_list = [“极客”，“gfg”]
> 
> **输出:** { '极客':[23，27]，' gfg': [0，2]}
> 
> **说明:**“极客”从索引号 23 开始，一直到 27，结果如此。

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/) **+** [**索引()**](https://www.geeksforgeeks.org/python-list-index/) **+ len()**

在这种情况下，循环用于从列表中获取每个元素。index()获取初始索引，len()获取字符串列表中所有元素的最后一个索引。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Start and End Indices of words from list in String
# Using loop + index() + len()

# initializing string
test_str = "gfg is best for all CS geeks and engineering job seekers"

# printing original string
print("The original string is : " + str(test_str))

# initializing check_list 
check_list = ["geeks", "engineering", "best", "gfg"]

res = dict()
for ele in check_list :
    if ele in test_str:

        # getting front index 
        strt = test_str.index(ele)

        # getting ending index
        res[ele] = [strt, strt + len(ele) - 1]

# printing result
print("Required extracted indices  : " + str(res))
```

**输出:**

> 原字符串是:gfg 最适合所有 CS 极客和工程求职者
> 
> 必需的提取索引:{“极客”:[23，27]，“工程”:[33，43]，“最佳”:[7，10]，“gfg”:[0，2]}

**方法二:使用** [**词典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/) **+ len() + index()**

在这种情况下，我们执行类似于上述功能的任务，但是结果字典的构建是使用使用字典理解的速记来完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Start and End Indices of words from list in String
# Using dictionary comprehension + len() + index()

# initializing string
test_str = "gfg is best for all CS geeks and engineering job seekers"

# printing original string
print("The original string is : " + str(test_str))

# initializing check_list
check_list = ["geeks", "engineering", "best", "gfg"]

# Dictionary comprehension to be used as shorthand for
# forming result Dictionary
res = {key: [test_str.index(key), test_str.index(key) + len(key) - 1]
       for key in check_list if key in test_str}

# printing result
print("Required extracted indices  : " + str(res))
```

**输出:**

> 原字符串是:gfg 最适合所有 CS 极客和工程求职者
> 
> 必需的提取索引:{“极客”:[23，27]，“工程”:[33，43]，“最佳”:[7，10]，“gfg”:[0，2]}
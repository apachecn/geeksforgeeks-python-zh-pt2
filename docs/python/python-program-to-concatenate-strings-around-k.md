# Python 程序连接 K 周围的字符串

> 原文:[https://www . geesforgeks . org/python-program-to-concatenate-strings-环绕-k/](https://www.geeksforgeeks.org/python-program-to-concatenate-strings-around-k/)

给定字符串列表，连接出现在字符串 k 周围的所有字符串

> **输入**:test _ list =[“Gfg”、“*”、“is”、“best”、“*”、“love”、“Gfg”]、K =“*”
> **输出**:[‘Gfg * is’，‘best * love’，‘Gfg’]
> **:周围所有元素都加入。**
> 
> ****输入**:test _ list =[“Gfg”，“{ content }”# x201；、“是”、“最好”、“内容{content}”、“爱”、“gfg”]、K =“{ content }”# x201；
> **输出** : ['Gfg$is '，' best$love '，' gfg']
> **说明**:$周围所有元素都加入。**

****方法 1:使用**一个**循环****

**这是执行这项任务的一种粗暴的方式。在这种情况下，我们遍历所有元素并检查 K，如果发现，我们执行与前面和后面的元素所需的连接。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of
# Concatenate Strings on K String
# Using loop

# initializing list
test_list = ["Gfg",  "+", "is", "best", "+", "love", "gfg"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K for Concatenate
K = "+"

res = []
idx = 0

while idx < len(test_list):

    ele = test_list[idx]

    # concatenation if next symbol is K
    if (idx < len(test_list) - 1) and test_list[idx + 1] == K:
        ele = ele + K + test_list[idx + 2]

        # increasing counter by 2
        idx += 2
    res.append(ele)
    idx += 1

# printing result
print("Strings after required concatenation : " + str(res))
```

****Output**

```
The original list is : ['Gfg', '+', 'is', 'best', '+', 'love', 'gfg']
Strings after required concatenation : ['Gfg+is', 'best+love', 'gfg']

```** 

 ****方法二:使用**[**join()**](https://www.google.com/search?q=join()+in+python&rlz=1C1CHZL_enIN830IN830&oq=join()&aqs=chrome.0.35i39j69i57j0l6.2090j0j7&sourceid=chrome&ie=UTF-8)**+**[**替换()**](https://www.google.com/search?rlz=1C1CHZL_enIN830IN830&sxsrf=ALeKk026x66LrRE0gP5wndlODSJTMGWKSQ%3A1599745192107&ei=qCxaX-6XBpaW4-EPsrSxwAg&q=replace%28%29+in+python&oq=replace%28%29+&gs_lcp=CgZwc3ktYWIQAxgAMgUIABCRAjICCAAyAggAMgIIADICCAAyAggAMgIIADICCAAyAggAMgIIADoECAAQR1CSFliSFmDtIGgAcAV4AIABigGIAYoBkgEDMC4xmAEAoAEBqgEHZ3dzLXdpesABAQ&sclient=psy-ab)**+**[**split()**](https://www.google.com/search?q=split()+in+python&rlz=1C1CHZL_enIN830IN830&oq=split()&aqs=chrome.0.69i59j69i57j0l5j69i61.2254j0j7&sourceid=chrome&ie=UTF-8)**

**上述功能的组合可以用来解决这个问题。在这种情况下，我们执行所有元素的连接，然后移除目标 k 周围的空间。被视为单个字符串，拆分所需的字符串会在 k 周围产生连接的值**

## **蟒蛇 3**

```
# initializing list
test_list = ["Gfg",  "+", "is", "best", "+", "love", "gfg"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K for Concatenate
K = "+"

# performing split after removing space around K
# splits assuming Strings joined around K
res = ' '.join(test_list).replace(' ' + K + ' ', K).split()

# printing result
print("Strings after required concatenation : " + str(res))
```

****Output**

```
The original list is : ['Gfg', '+', 'is', 'best', '+', 'love', 'gfg']
Strings after required concatenation : ['Gfg+is', 'best+love', 'gfg']

```**
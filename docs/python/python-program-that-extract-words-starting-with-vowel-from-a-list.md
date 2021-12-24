# 从列表中提取以元音开头的单词的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-从列表中提取单词的程序-以元音开头/](https://www.geeksforgeeks.org/python-program-that-extract-words-starting-with-vowel-from-a-list/)

给定一个包含字符串元素的列表，下面的程序提取那些以元音开头的元素(a，e，I，o，u)。

> **输入**:test _ list =[“all”、“love”、“get”、“educed”、“by”、“gfg”]
> **输出**:[‘all’，‘educed’]
> **解释** : a、e 均为元音，遂提取单词。
> **输入**:test _ list =[“all”、“love”、“get”、“educed”、“by”、“agfg”]
> **输出**:[“all”、“educed”、“agfg”]
> **解释** : a、e、a 均为元音，遂词提取。

**方法 1 :** *使用*[*starts with()*](https://www.geeksforgeeks.org/python-startswith-endswidth-function/#:~:text=Use%20%3A,to%20be%20considered%20for%20searching.)*和* [*loop*](https://www.geeksforgeeks.org/loops-in-python/)

在本文中，我们检查每个单词，并在每个单词的第一个字母表中使用 starts with()检查它是否以元音开头。迭代部分使用循环完成。

## 蟒蛇 3

```py
# initializing list
test_list = ["all", "love", "and", "get", "educated", "by", "gfg"]

# printing original list
print("The original list is : " + str(test_list))

res = []
vow = "aeiou"
for sub in test_list:
    flag = False

    # checking for begin char
    for ele in vow:
        if sub.startswith(ele):
            flag = True 
            break
    if flag:
        res.append(sub)

# printing result 
print("The extracted words : " + str(res))
```

**输出:**

> 原列表为:['all '，' love '，' and '，' get '，' educed '，' by '，' gfg']
> 提取的词:['all '，' and '，' educed ']

**方法二:** *使用* [*任意()*](https://www.geeksforgeeks.org/any-all-in-python/)*[*starts with()*](https://www.geeksforgeeks.org/python-startswith-endswidth-function/#:~:text=Use%20%3A,to%20be%20considered%20for%20searching.)*和* [*loop*](https://www.geeksforgeeks.org/loops-in-python/)*

*在这种情况下，我们使用 any()检查元音，其余所有功能与上述方法类似。*

## *蟒蛇 3*

```py
*# initializing list
test_list = ["all", "love", "and", "get", "educated", "by", "gfg"]

# printing original list
print("The original list is : " + str(test_list))

res = []
vow = "aeiou"
for sub in test_list:

    # check for vowel beginning
    flag = any(sub.startswith(ele) for ele in vow)

    if flag:
        res.append(sub)

# printing result 
print("The extracted words : " + str(res))*
```

***输出:***

> *原列表为:['all '，' love '，' and '，' get '，' educed '，' by '，' gfg']
> 提取的词:['all '，' and '，' educed ']*
# 打印列表元素指定索引处公共元素的 Python 程序

> 原文:[https://www . geesforgeks . org/python-print-program-elements-common-at-specific-index-of-list-elements/](https://www.geeksforgeeks.org/python-program-that-prints-elements-common-at-specified-index-of-list-elements/)

给定一个字符串列表，任务是编写一个 Python 程序来提取列表中每个元素的指定索引处相同的所有字符。

> **输入** : test_list = [“极客”、“弱者”、“鸟嘴”、“peek”]
> **输出**:[‘e’，‘k’]
> **解释** : e 和 k 在所有字符串的索引处相同。
> 
> **输入** : test_list = [“极客”、“弱者”、“鸟嘴”、“同行”]
> **输出** : ['e']
> **解释** : e 在所有字符串的索引处相同。

**方法 1 :** *使用*[*min()*](https://www.geeksforgeeks.org/python-min-function/)*[*len()*](https://www.geeksforgeeks.org/python-string-length-len/)和 [*loop*](https://www.geeksforgeeks.org/python-for-loops/)*

*在这种情况下，最初提取最小长度字符串来检查要迭代的索引，以确保字符串中的所有索引。然后使用循环检查每个索引中是否有相似的字符，如果找到，将字符追加到结果中。*

## *蟒蛇 3*

```
*# initializing Matrix
test_list = ["geeks", "weak", "beak", "peek"]

# printing original list
print("The original list is : " + str(test_list))

# getting min length string
min_len = min(len(ele) for ele in test_list)

res = []
for idx in range(0, min_len):
    flag = True
    for ele in test_list:

        # checking for all equal columns
        if ele[idx] != test_list[0][idx]:
            flag = False
            break

    if flag:
        res.append(test_list[0][idx])

# printing result
print("Extracted similar characters : " + str(res))*
```

***输出:***

> *最初的名单是:['极客'，'弱者'，'鸟嘴'，'窥视'*
> 
> *提取的相似字符:['e '，' k']*

***方法二:** *使用* [*all()*](https://www.geeksforgeeks.org/any-all-in-python/) *、*[*min()*](https://www.geeksforgeeks.org/python-min-function/)*、*[*len()*](https://www.geeksforgeeks.org/python-string-length-len/)*和* [*循环*](https://www.geeksforgeeks.org/python-for-loops/)*

*在本例中，我们使用 all()执行检查所有元素是否匹配的任务，减少了嵌套循环，增加了可读性。*

## *蟒蛇 3*

```
*# initializing Matrix
test_list = ["geeks", "weak", "beak", "peek"]

# printing original list
print("The original list is : " + str(test_list))

# getting min length string
min_len = min(len(ele) for ele in test_list)

res = []
for idx in range(0, min_len):

    # using all() for condition injection
    if all(ele[idx] == test_list[0][idx] for ele in test_list):
        res.append(test_list[0][idx])

# printing result
print("Extracted similar characters : " + str(res))*
```

***输出:***

> *最初的名单是:['极客'，'弱者'，'鸟嘴'，'窥视'*
> 
> *提取的相似字符:['e '，' k']*
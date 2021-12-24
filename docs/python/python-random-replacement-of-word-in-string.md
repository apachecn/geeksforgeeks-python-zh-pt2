# Python–字符串中单词的随机替换

> 原文:[https://www . geesforgeks . org/python-随机替换字符串中的单词/](https://www.geeksforgeeks.org/python-random-replacement-of-word-in-string/)

给定一个字符串和列表，用列表中的随机元素替换字符串中 K 个单词的每次出现。

> **输入**:test _ str =“Gfg 为 x .其也 x 为极客”，repl_list = [“好”、“更好”、“最好”]，repl _ word =“x”
> **输出** : Gfg 为最佳。对极客来说也更好
> **解释** : x 被随机替换列表值替换。
> 
> **输入**:test _ str =“Gfg 为 x .其也 x 为极客”，repl_list = [“好”、“更好”、“好听”]，repl _ word =“x”
> **输出** : Gfg 为最佳。对极客来说也很好
> **解释** : x 被随机替换列表值“最佳”和“很好”代替。

**方法#1:使用 shuffle() + loop + replace()**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 replace()从列表中用随机字符串替换 K 个单词的每个出现。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Random Replacement of Word in String
# Using replace() + shuffle() + loop
from random import shuffle

# initializing string
test_str = "Gfg is val. Its also val for geeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing list 
repl_list = ["Good", "Better", "Best"]

# initializing replace word
repl_word = "val"

# shuffing list order
shuffle(repl_list)
for ele in repl_list:

    # replacing with random string 
    test_str = test_str.replace(repl_word, ele, 1)

# printing result 
print("String after random replacement : " + str(test_str)) 
```

**Output**

```
The original string is : Gfg is val. Its also val for geeks
String after random replacement : Gfg is Best. Its also Better for geeks

```

**方法 2:使用列表理解+替换()+洗牌()**

这是执行这项任务的方法之一。在这种情况下，我们使用与上述方法类似的功能将整个逻辑封装在一行中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Random Replacement of Word in String
# Using list comprehension + replace() + shuffle()
from random import shuffle

# initializing string
test_str = "Gfg is val. Its also val for geeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing list 
repl_list = ["Good", "Better", "Best"]

# initializing replace word
repl_word = "val"

# one-liner to solve problem
shuffle(repl_list)
res = [test_str.replace(repl_word, ele, 1) for ele in repl_list]

# printing result 
print("String after random replacement : " + str(res)) 
```

**Output**

> 原始字符串是:Gfg 是 val。随机替换后的极客
> 字符串也有价值:['Gfg 好。它对极客来说也很有价值。它对极客来说也很有价值。这也是极客价值所在。]
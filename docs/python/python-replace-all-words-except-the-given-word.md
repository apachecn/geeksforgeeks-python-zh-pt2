# Python–替换除给定单词之外的所有单词

> 原文:[https://www . geesforgeks . org/python-替换除给定单词之外的所有单词/](https://www.geeksforgeeks.org/python-replace-all-words-except-the-given-word/)

给定一个字符串。任务是用“？”替换所有单词除了给定的单词 k。

**示例:**

> **输入** : test_str = 'gfg 最适合极客'，K = "gfg "，repl_char = "？"
> **输出** : gfg？？？？
> **解释**:除 gfg 外的所有单词都替换为？。
> 
> **输入** : test_str = 'gfg 最适合 gfg '，K = "gfg "，repl_char = "？"
> **输出** : gfg？？？gfg
> **解释**:除 gfg 外的所有单词都替换为？。

**方法#1:使用 split() + join() +循环**

这是执行这项任务的一种粗暴的方式。在本例中，我们使用 [split()](https://www.geeksforgeeks.org/python-string-split/) 执行将字符串更改为单词列表的任务，然后检查 K 个单词，如果没有找到，则用适当的值替换它。最后，使用 [join()](https://www.geeksforgeeks.org/join-function-python/) 转换回字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Replace all words not K
# Using join() + split() + loop

# initializing string
test_str = 'gfg is best for geeks gfg is for cs I love gfg'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = "gfg"

# initializing repl_char
repl_char = "?"

# extracting words
temp = test_str.split(" ")
for idx in range(len(temp)):
    ele = temp[idx]

    # replace non K with repl_char
    if not ele == K:
        temp[idx] = repl_char

# joining result
res = " ".join(temp)

# printing result
print("The resultant string : " + str(res))
```

**输出:**

> 原串是:gfg 最适合极客 gfg 是 cs 我爱 gfg
> 结果串:gfg？？？？gfg？？？？？gfg

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

这是执行这项任务的另一种方式。在这种情况下，我们迭代元素，并使用与上述方法类似的功能使用一行代码执行任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Replace all words not K
# Using list comprehension

# initializing string
test_str = 'gfg is best for geeks gfg is for cs I love gfg'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = "gfg"

# initializing repl_char
repl_char = "?"

# using one-liner to solve this problem
res = " ".join(
    [repl_char if not ele == K else ele for ele in test_str.split()])

# printing result
print("The resultant string : " + str(res))
```

**输出:**

> 原串是:gfg 最适合极客 gfg 是 cs 我爱 gfg
> 结果串:gfg？？？？gfg？？？？？gfg
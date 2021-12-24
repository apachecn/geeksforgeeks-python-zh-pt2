# Python 程序替换列表中除给定字符以外的所有字符

> 原文:[https://www . geesforgeks . org/python-程序替换列表中除给定字符之外的所有字符/](https://www.geeksforgeeks.org/python-program-to-replace-all-characters-of-a-list-except-the-given-character/)

给定一个列表。任务是用 N 替换列表中除给定字符之外的所有字符。

> **输入** : test_list = ['G '，' F '，' G '，' I '，' S '，' B '，' E '，' S '，' T']，repl_chr = '* '，ret_chr = 'G'
> **输出** : ['G '，' * ' G '，' * '，' * '，' *，' * '，' *']
> **说明:**除 G 以外的所有字符替换为*
> 
> **输入** : test_list = ['G '，' F '，' G '，' B '，' E '，' S '，' T']，repl_chr = '* '，ret_chr = 'G'
> **输出** : ['G '，' * '，' G '，' * '，' *，' *]
> **解释**:除 G 以外的所有字符替换为*

**方法一:使用列表理解+条件表达式**

在本文中，我们使用列表理解执行迭代任务，并使用条件运算符处理替换。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Replace all Characters Except K
# Using list comprehension and conditional expressions

# initializing lists
test_list = ['G', 'F', 'G', 'I', 'S', 'B', 'E', 'S', 'T']

# printing original list
print("The original list : " + str(test_list))

# initializing repl_chr
repl_chr = '{content}apos;

# initializing retain chararter
ret_chr = 'G'

# list comprehension to remake list after replacement
res = [ele if ele == ret_chr else repl_chr for ele in test_list]

# printing result
print("List after replacement : " + str(res))
```

**Output**

```py
The original list : ['G', 'F', 'G', 'I', 'S', 'B', 'E', 'S', 'T']
List after replacement : ['G', '{content}apos;, 'G', '{content}apos;, '{content}apos;, '{content}apos;, '{content}apos;, '{content}apos;, '{content}apos;]

```

**方法 2:使用 map() + lambda**

在本文中，我们使用 map()和 lambda 函数将逻辑扩展到列表的每个元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Replace all Characters Except K
# Using map() + lambda

# initializing lists
test_list = ['G', 'F', 'G', 'I', 'S', 'B', 'E', 'S', 'T']

# printing original list
print("The original list : " + str(test_list))

# initializing repl_chr
repl_chr = '{content}apos;

# initializing retain chararter
ret_chr = 'G'

# using map() to extend logic to each element of list
res = list(map(lambda ele: ret_chr if ele == ret_chr else repl_chr, test_list))

# printing result
print("List after replacement : " + str(res))
```

**Output**

```py
The original list : ['G', 'F', 'G', 'I', 'S', 'B', 'E', 'S', 'T']
List after replacement : ['G', '{content}apos;, 'G', '{content}apos;, '{content}apos;, '{content}apos;, '{content}apos;, '{content}apos;, '{content}apos;]

```
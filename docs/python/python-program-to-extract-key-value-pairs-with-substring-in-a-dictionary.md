# Python 程序提取字典中带有子串的键值对

> 原文:[https://www . geeksforgeeks . org/python-用字典中的子串提取键值对的程序/](https://www.geeksforgeeks.org/python-program-to-extract-key-value-pairs-with-substring-in-a-dictionary/)

给定一个字典列表，提取所有子串出现在特定关键字中的字典。

> **输入**:[{“Gfg”:“4”、“最佳”:“1”}、{“Gfg”:“好 CS 内容”、“最佳”:“10”}]、K =“Gfg”、sub _ str =“CS”
> **输出**:[{“Gfg”:“好 CS 内容”、“最佳”:“10”}]
> **解释**:“Gfg”有“CS”作为子串值。
> 
> **输入**:[{“Gfg”:“4”、“最佳”:“1”}、{“Gfg”:“内容好”、“最佳”:“10”}]、K =“Gfg”、sub _ str =“CS”
> **输出**:【】
> **解释**:没有以“CS”为子串的字典来“Gfg”键。

**方法一:使用列表理解**

这是执行这项任务的方法之一。在这种情况下，我们迭代所有字典，并使用 In 运算符检查键的值子串是否存在。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Dictionaries with Substring values
# Using list comprehension

# initializing lists
test_list = [{"Gfg": "4", "best": "1"},
             {"Gfg": "good for CS", "best": "8"},
             {"Gfg": "good CS content", "best": "10"}]

# printing original list
print("The original list : " + str(test_list))

# initializing K key
K = "Gfg"

# initializing target value
sub_str = "CS"

# list comprehension to extract values with
# substring values using in operator
res = [val for val in test_list if sub_str in val[K]]

# printing result
print("Dictionaries with particular substring values : " + str(res))
```

**输出:**

> 原始列表:[{'Gfg': '4 '，' best': '1'}，{'Gfg ':'适合 CS '，' best': '8'}，{'Gfg ':'适合 CS 内容'，' best': '10'}]
> 具有特定子字符串值的词典:[{'Gfg ':'适合 CS '，' best': '8'}，{'Gfg ':'适合 CS 内容'，' best': '10'}]

**方法 2:在运算符**中使用 map() +

这是执行这项任务的另一种方式。在这种情况下，我们使用 map() + lambda 函数提取具有所需子串的所有值。in 运算符用于检查键值内部的子字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Dictionaries with Substring values
# Using map() + in operator

# initializing lists
test_list = [{"Gfg": "4", "best": "1"},
             {"Gfg": "good for CS", "best": "8"},
             {"Gfg": "good CS content", "best": "10"}]

# printing original list
print("The original list : " + str(test_list))

# initializing K key
K = "Gfg"

# initializing target value
val = "CS"

# map() used to perform filtering
res = list(map(lambda sub: val in sub[K], test_list))
res = [test_list[idx] for idx, ele in enumerate(res) if res[idx]]

# printing result
print("Dictionaries with particular substring values : " + str(res))
```

**输出:**

> 原始列表:[{'Gfg': '4 '，' best': '1'}，{'Gfg ':'适合 CS '，' best': '8'}，{'Gfg ':'适合 CS 内容'，' best': '10'}]
> 具有特定子字符串值的词典:[{'Gfg ':'适合 CS '，' best': '8'}，{'Gfg ':'适合 CS 内容'，' best': '10'}]
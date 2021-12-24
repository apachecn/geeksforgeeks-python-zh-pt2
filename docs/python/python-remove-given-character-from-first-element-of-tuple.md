# Python–从元组的第一个元素中移除给定字符

> 原文:[https://www . geesforgeks . org/python-从元组的第一个元素中移除给定字符/](https://www.geeksforgeeks.org/python-remove-given-character-from-first-element-of-tuple/)

给定一个元组列表，从作为字符串的元组的第一个元素中删除 K 个字符。

> **输入**:test _ list =[(“GF $ g！”, 5), ("!i$s "，4)、(“最好！{ content } # x201D，10)]，K = ' { content } '；
> **输出** : [('GFg！', 5), ('!是'，4)，('最好！，10)]
> **解释**:第一个元素的字符串 K 值被移除。
> 
> **输入**:test _ list =[(“GF $ g！”，5)、(“最好！{ content } # x201D，10)]，K = ' { content } '；
> **输出** : [('GFg！，5)，('最好！，10)]
> **解释**:第一个元素的字符串 K 值被移除。

**方法一:使用 replace() +列表理解**

在这种情况下，我们使用 replace()来执行 K 字符的移除任务和列表理解来重组元组。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove K character from first element of Tuple
# Using replace() + list comprehension

# initializing list
test_list = [("GF ! g !", 5), ("! i ! s", 4), ("best !!", 10)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = "!"

# replace with empty string removes the desired char.
res = [(sub[0].replace(K, ''), sub[1]) for sub in test_list]

# printing result 
print("The filtered tuples : " + str(res))
```

**Output**

```py
The original list is : [('GF!g!', 5), ('!i!s', 4), ('best!!', 10)]
The filtered tuples : [('GFg', 5), ('is', 4), ('best', 10)]

```

**方法 2:使用 translate() +列表理解**

在本例中，我们使用 translate()执行移除任务，该任务需要使用 order()转换为 ascii，并替换为空字符。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove K character from first element of Tuple
# Using translate() + list comprehension

# initializing list
test_list = [("GF ! g !", 5), ("! i ! s", 4), ("best !!", 10)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = "!"

# translation after conversion to ascii number 
res = [(sub[0].translate({ord(K): None}), sub[1]) for sub in test_list]

# printing result 
print("The filtered tuples : " + str(res))
```

**Output**

```py
The original list is : [('GF!g!', 5), ('!i!s', 4), ('best!!', 10)]
The filtered tuples : [('GFg', 5), ('is', 4), ('best', 10)]

```
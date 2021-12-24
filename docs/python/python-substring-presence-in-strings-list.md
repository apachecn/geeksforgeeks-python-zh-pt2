# Python–字符串列表中存在子字符串

> 原文:[https://www . geesforgeks . org/python-substring-in-strings-list/](https://www.geeksforgeeks.org/python-substring-presence-in-strings-list/)

给定子字符串列表和字符串列表，检查每个子字符串，如果它们存在于列表中的任何字符串中。

> **输入**:test _ list 1 =[“Gfg”，“is”，“Best”]，test_list2 = [“我爱 Gfg”，“它最适合极客”，“Gfg 的意思是 CS”]
> **输出**:【真，假，假】
> **解释**:在第 2 个列表中的任何列表字符串中，只有 Gfg 作为子字符串出现。
> 
> **输入**:test _ list 1 =[“Gfg”、“is”、“Best”]，test_list2 = [“我爱 Gfg”、“最适合极客”、“Gfg 的意思是 CS”]
> **输出**:【真、真、假】
> **解释**:在第 2 个列表中的任意列表字符串中，只有 Gfg 和 is 作为子字符串出现。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在本例中，我们为列表中的每个元素检查它是否是任何其他列表元素的子串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Substring presence in Strings List
# Using loop

# initializing lists
test_list1 = ["Gfg", "is", "Best"]
test_list2 = ["I love Gfg", "Its Best for Geeks", "Gfg means CS"]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using loop to iterate
res = []
for ele in test_list1 :
  temp = False

  # inner loop to check for
  # presence of element in any list
  for sub in test_list2 :
    if ele in sub:
      temp = True
      break    
  res.append(temp)

# printing result 
print("The match list : " + str(res))
```

**Output**

```
The original list 1 : ['Gfg', 'is', 'Best']
The original list 2 : ['I love Gfg', 'Its Best for Geeks', 'Gfg means CS']
The match list : [True, False, True]

```

**方法 2:使用列表理解+任意()**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 any()检查任何子列表，并使用列表理解来执行迭代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Substring presence in Strings List
# Using list comprehension + any()

# initializing lists
test_list1 = ["Gfg", "is", "Best"]
test_list2 = ["I love Gfg", "Its Best for Geeks", "Gfg means CS"]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# any() reduces a nesting
# checks for element presence in all Substrings
res = [True if any(i in j for j in test_list2) else False for i in test_list1]

# printing result 
print("The match list : " + str(res))
```

**Output**

```
The original list 1 : ['Gfg', 'is', 'Best']
The original list 2 : ['I love Gfg', 'Its Best for Geeks', 'Gfg means CS']
The match list : [True, False, True]

```
# Python–单词的序列赋值

> 原文:[https://www . geesforgeks . org/python-sequence-赋值-to-word/](https://www.geeksforgeeks.org/python-sequence-assignment-to-words/)

给定一串单词，给每个单词分配一个索引。

> **输入**:test _ str = ' geekforgeks is best '
> **输出**:{ 0:' geekforgeks '，1: 'is '，2: 'best'}
> **解释**:索引赋给每个单词。
> 
> **输入**:test _ str = ' geek forgek best '
> **输出**:{ 0:' geek forgek '，1: 'best'}
> **解释**:为每个单词分配的索引。

**方法#1:使用 enumerate() + dict() + split()**

在这种情况下，我们首先执行 split()任务，然后使用 enumerate()添加索引组件来映射每个带有索引的单词。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sequence Assignment to Words
# Using split() + enumerate() + dict()

# initializing string
test_str = 'geekforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# using dict() to convert result in idx:word manner 
res = dict(enumerate(test_str.split()))

# printing result 
print("The Assigned Sequence : " + str(res)) 
```

**Output**

```
The original string is : geekforgeeks is best for geeks
The Assigned Sequence : {0: 'geekforgeeks', 1: 'is', 2: 'best', 3: 'for', 4: 'geeks'}

```

**方法 2:使用 zip() + count() + dict()**

在这种情况下，count()组件呈现索引逻辑，每个单词与索引的配对是使用 zip()完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sequence Assignment to Words
# Using zip() + count() + dict()
from itertools import count

# initializing string
test_str = 'geekforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# using dict() to convert result in idx:word manner 
# count() from itertools used for this task
res = dict(zip(count(), test_str.split()))

# printing result 
print("The Assigned Sequence : " + str(res)) 
```

**Output**

```
The original string is : geekforgeeks is best for geeks
The Assigned Sequence : {0: 'geekforgeeks', 1: 'is', 2: 'best', 3: 'for', 4: 'geeks'}

```
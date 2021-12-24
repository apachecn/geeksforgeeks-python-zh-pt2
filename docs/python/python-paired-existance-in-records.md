# Python–记录中的配对存在

> 原文:[https://www . geesforgeks . org/python-paint-existence-in-records/](https://www.geeksforgeeks.org/python-paired-existance-in-records/)

有时候，在处理 Python 记录时，我们可能会遇到一个问题，需要检查记录中是否存在成对的记录，否则如果一个不存在，其他的也不应该存在。这种问题在数据科学和网络开发等领域很常见。让我们讨论执行这项任务的某些方法。

> **输入** :
> test_list = [('Gfg '，' is '，' Best ')，(' Gfg '，' is '，' good ')，(' CS '，' is '，' good')]
> 对= ('is '，' good ')
> T5】输出 : [('Gfg '，' is '，' good ')，(' CS '，' is '，' good')]
> **输入** :
> test_list = [('Gfg '，' is '，' Best ')，(' Gfg '，' is '，' good ')

**方法#1:使用生成器表达式**
这是可以执行该任务的蛮力方式。在这种情况下，我们检查两个数字的存在/不存在，如果没有或两个数字都存在，则接受结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Paired Existence in Records
# Using generator expression

# initializing list
test_list = [('Gfg', 'is', 'Best'),
             ('Gfg', 'is', 'good'),
             ('CS', 'is', 'good')]

# printing original list
print("The original list is : " + str(test_list))

# initializing Pairs
pairs = ('Gfg', 'Best')

# Paired Existence in Records
# Using generator expression
res = []
for sub in test_list:
    if ((pairs[0] in sub and pairs[1] in sub) or (
         pairs[0] not in sub and pairs[1] not in sub)):
        res.append(sub)

# printing result
print("The resultant records : " + str(res))
```

**Output : **

原始列表为:[('Gfg '，' is '，' Best ')，(' Gfg '，' is '，' good ')，(' CS '，' is '，' good')]
结果记录:[('Gfg '，' is '，' Best ')，(' CS '，' is '，' good')]

**方法 2:使用 XNOR**
这是解决这个问题的又一种方法。在这种情况下，使用异或运算符的幂来执行此任务并否定结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Paired Existence in Records
# Using XNOR

# initializing list
test_list = [('Gfg', 'is', 'Best'),
             ('Gfg', 'is', 'good'),
             ('CS', 'is', 'good')]

# printing original list
print("The original list is : " + str(test_list))

# initializing Pairs
pairs = ('Gfg', 'Best')

# Paired Existence in Records
# Using XNOR
res = []
for sub in test_list:
    if (not ((pairs[0] in sub) ^ (pairs[1] in sub))):
        res.append(sub)

# printing result
print("The resultant records : " + str(res))
```

**Output : **

```
The original list is : [('Gfg', 'is', 'Best'), ('Gfg', 'is', 'good'), ('CS', 'is', 'good')]
The resultant records : [('Gfg', 'is', 'Best'), ('CS', 'is', 'good')]
```
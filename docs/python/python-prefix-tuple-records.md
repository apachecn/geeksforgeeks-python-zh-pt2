# Python–前缀元组记录

> 原文:[https://www.geeksforgeeks.org/python-prefix-tuple-records/](https://www.geeksforgeeks.org/python-prefix-tuple-records/)

有时，在使用 Python 列表时，我们可能会遇到这样的问题，即我们需要找到以特定元组记录开始的所有元组。这种问题可以在数据领域中找到应用。让我们讨论执行这项任务的某些方法。
**方法#1:使用列表理解+ zip() + all()**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 all()执行检查任务，该任务检查所有前缀元素与使用 zip()压缩前缀的元素是否相等。列表理解用于执行所有元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Prefix tuple records
# Using list comprehension + zip() + all()

# initializing list
test_list = [('Gfg', 'best', 'geeks'), ('Gfg', 'good'),
             ('Gfg', 'best', 'CS'), ('Gfg', 'love')]

# printing original list
print("The original list is : " + str(test_list))

# initializing prefix tuple
pref_tup = ('Gfg', 'best')

# Prefix tuple records
# Using list comprehension + zip() + all()
res = [tup for tup in test_list if all(x == y for x, y in
                                     zip(tup, pref_tup))]

# printing result
print("The filtered tuples : " + str(res))
```

**Output : **

原列表为:[('Gfg '，' best '，' geeks ')，(' Gfg '，' best '，' CS ')，(' Gfg '，' love')]
过滤后的元组:[('Gfg '，' best '，' geeks ')，(' Gfg '，' best '，' CS')]

**方法#2:使用 filter() + lambda +生成器表达式+ all()**
以上函数的组合可以用来解决这个特定的问题。在本文中，我们使用 filter()执行过滤任务，使用 lambda 函数执行逻辑编译。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Prefix tuple records
# Using filter() + lambda + generator expression + all()

# initializing list
test_list = [('Gfg', 'best', 'geeks'), ('Gfg', 'good'),
                 ('Gfg', 'best', 'CS'), ('Gfg', 'love')]

# printing original list
print("The original list is : " + str(test_list))

# initializing prefix tuple
pref_tup = ('Gfg', 'best')

# Prefix tuple records
# Using filter() + lambda + generator expression + all()
res = list(filter(lambda sub: all([sub[idx] == ele
      for idx, ele in enumerate(pref_tup)]), test_list))

# printing result
print("The filtered tuples : " + str(res))
```

**Output : **

原列表为:[('Gfg '，' best '，' geeks ')，(' Gfg '，' best '，' CS ')，(' Gfg '，' love')]
过滤后的元组:[('Gfg '，' best '，' geeks ')，(' Gfg '，' best '，' CS')]
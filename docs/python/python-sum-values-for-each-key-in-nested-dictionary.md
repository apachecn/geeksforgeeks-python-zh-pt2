# Python |嵌套字典中每个键的总和值

> 原文:[https://www . geesforgeks . org/python-嵌套字典中每个键的和值/](https://www.geeksforgeeks.org/python-sum-values-for-each-key-in-nested-dictionary/)

给定一个嵌套字典，我们必须在那个嵌套字典中找到特定值的和。这在给我们一个 JSON 对象或者我们已经抓取了一个特定的页面并且我们想要对对象中特定属性的值求和的情况下基本上是有用的。

**代码#1:** 使用 sum()函数

```py
# Python code to find sum values within nested dictionaries
weapons = {'': None, 'sword': { 'steel': 151,
                                'sharpness': 100,
                                'age': 2,},

                     'arrow': {'steel': 120,
                               'sharpness': 205,
                               'age': 1,}}

sumValue1 = sum(d['sharpness'] for d in weapons.values() if d)
sumValue2 = sum(d['steel'] for d in weapons.values() if d)

print(sumValue1)
print(sumValue2)
```

**求锐度值之和输出:**

```py
305
271

```
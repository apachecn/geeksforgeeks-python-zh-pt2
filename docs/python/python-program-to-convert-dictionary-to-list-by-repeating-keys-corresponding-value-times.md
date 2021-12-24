# Python 程序通过重复按键对应的值次数将字典转换为列表

> 原文:[https://www . geesforgeks . org/python-程序到转换-字典到列表-通过重复键-对应值-时间/](https://www.geeksforgeeks.org/python-program-to-convert-dictionary-to-list-by-repeating-keys-corresponding-value-times/)

给定一个字典，其中键是字符，它们的组成值是数字，这里的任务是编写一个 python 程序，它可以通过重复键字符值多次将其转换为列表。

> **输入:** test_dict = {'g' : 2，' f' : 3，' g' : 1，' b' : 4，' e' : 1，' s' : 4，' t' : 3}
> 
> **输出:** ['g '，' f '，' f '，' f '，' b '，' b '，' b '，' e '，' s '，' s '，' s '，' t '，' t '
> 
> **说明:** f 在列表中增加 3 次。
> 
> **输入:** test_dict = {'g' : 2，' f' : 3，' g' : 1，' b' : 4，' e' : 1}
> 
> **输出** : ['g '，' f '，' f '，' b '，' b '，' b '，' e']
> 
> **说明**:列表中 f 增加 3 次。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [**运算符*](https://www.geeksforgeeks.org/python-operators/)

在这种情况下，使用循环插入元素，使用*运算符处理事件。

**程序:**

## 蟒蛇 3

```py
# initializing dictionary
test_dict = {'g': 2, 'f': 3, 'g': 1, 'b': 4, 'e': 1, 's': 4, 't': 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

res = []
for key, val in test_dict.items():

    # getting values using * operator
    res += [key] * val

# printing result
print("The constructed list : " + str(res))
```

**输出:**

> 原始词典为:{'g': 1，' f': 3，' b': 4，' e': 1，' s': 4，' t': 3}
> 
> 构造的列表:['g '，' f '，' f '，' f '，' b '，' b '，' b '，' e '，' s '，' s '，' s '，' t '，' t']

**方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

这使用嵌套循环方法，使用列表理解作为一个线性来解决这个问题。根据需要多次迭代这些值。

**程序:**

## 蟒蛇 3

```py
# initializing dictionary
test_dict = {'g': 2, 'f': 3, 'g': 1, 'b': 4, 'e': 1, 's': 4, 't': 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# nested list comprehension to solve problem
res = [key for key, val in test_dict.items() for _ in range(val)]

# printing result
print("The constructed list : " + str(res))
```

**输出:**

> 原始词典为:{'g': 1，' f': 3，' b': 4，' e': 1，' s': 4，' t': 3}
> 
> 构造的列表:['g '，' f '，' f '，' f '，' b '，' b '，' b '，' e '，' s '，' s '，' s '，' t '，' t']
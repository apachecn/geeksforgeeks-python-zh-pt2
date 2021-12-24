# Python 列表扩展()方法

> 原文:[https://www.geeksforgeeks.org/python-list-extend-method/](https://www.geeksforgeeks.org/python-list-extend-method/)

Python 的 List***extend()****方法迭代像字符串、列表、元组等可迭代的对象。，并将可迭代的每个元素添加到[列表](https://www.geeksforgeeks.org/python-list/)的末尾。列表的长度随着列表中元素的数量而增加。*

> ***语法:** list.extend(可迭代)*
> 
> ***参数:***
> 
>  **   **可迭代的:**任何可迭代的(列表、集合、元组等。)
> 
> **返回:**
> 
> extend()方法修改原始列表。它不返回值。*

### ***示例 1:使用**扩展()方法*

## *计算机编程语言*

```py
*# my_list
my_list = ['geeks', 'for']

# Another list
another_list = [6, 0, 4, 1]

# Using extend() method
my_list.extend(another_list)

print my_list*
```

***输出:***

```py
*['geeks', 'for', 6, 0, 4, 1]*
```

### ***示例 2:** 添加元组元素并设置为列表*

## *计算机编程语言*

```py
*# My List
my_list = ['geeks', 'for', 'geeks']

# My Tuple
my_tuple = ('DSA', 'Java')

# My Set
my_set = {'Flutter', 'Android'}

# Append tuple to the list
my_list.extend(my_tuple)

print(my_list)

# Append set to the list
my_list.extend(my_set)

print(my_list)*
```

***输出:***

```py
*['geeks', 'for', 'geeks', 'DSA', 'Java']
['geeks', 'for', 'geeks', 'DSA', 'Java', 'Android', 'Flutter']*
```

### ***示例 3:将字符串**扩展到列表*

*字符串是可迭代的，所以如果你用字符串扩展一个列表，当你迭代字符串时，你会附加每个字符。*

## *计算机编程语言*

```py
*# My list
my_list = ['geeks', 'for', 6, 0, 4, 1]

# My string
my_list.extend('geeks')

print my_list*
```

***输出:***

```py
*['geeks', 'for', 6, 0, 4, 1, 'g', 'e', 'e', 'k', 's']*
```
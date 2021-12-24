# 在 python 中设置 add()

> 原文:[https://www.geeksforgeeks.org/set-add-python/](https://www.geeksforgeeks.org/set-add-python/)

如果集合中没有给定的元素，set add()方法会将该元素添加到集合中。

**语法:**

```
set.add(elem)
The add() method doesn't add an element to the
set if it's already present in it otherwise it 
will get added to the set.
Parameters:
add() takes single parameter(elem) which needs to 
be added in the set.
Returns:
The add() method doesn't return any value.

```

```
# set of letters
GEEK = {'g', 'e', 'k'}

# adding 's'
GEEK.add('s')
print('Letters are:', GEEK)

# adding 's' again
GEEK.add('s')
print('Letters are:', GEEK)
```

输出:

```
('Letters are:', set(['k', 'e', 's', 'g']))
('Letters are:', set(['k', 'e', 's', 'g'])

```

**应用:**

```
It is used to add a new element to the set. 

```

```
# set of letters
GEEK = {6, 0, 4}

# adding 1
GEEK.add(1)
print('Letters are:', GEEK)

# adding 0 
GEEK.add(0)
print('Letters are:', GEEK)
```

输出:

```
('Letters are:', set([0, 1, 4, 6]))
('Letters are:', set([0, 1, 4, 6]))

```

 **向集合添加元组:**

```
# Python code to demonstrate addition of tuple to a set.
s = {'g', 'e', 'e', 'k', 's'}
t = ('f', 'o')

# adding tuple t to set s.
s.add(t)

print(s)
```

输出:

```
{'k', 's', 'e', 'g', ('f', 'o')}

```
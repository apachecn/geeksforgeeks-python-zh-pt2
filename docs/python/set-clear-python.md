# 在 python 中设置 clear()

> 原文:[https://www.geeksforgeeks.org/set-clear-python/](https://www.geeksforgeeks.org/set-clear-python/)

clear()方法从集合中移除所有元素。

**语法:**

```py
set.clear()
parameters:
The clear() method doesn't take any parameters.
Return:
The clear() method doesn't return any value.

```

```py
# set of letters
GEEK = {'g', 'e', 'e', 'k', 's'}
print('GEEK before clear:', GEEK)

# clearing vowels
GEEK.clear()
print('GEEK after clear:', GEEK)
```

输出:

```py
GEEK before clear: set(['s', 'e', 'k', 'g'])
GEEK after clear: set([])

```

**应用:**

```py
It is used to clear set.

```

```py
# set of letters
GEEK = {6, 0, 4, 1}
print('GEEK before clear:', GEEK)

# clearing vowels
GEEK.clear()
print('GEEK after clear:', GEEK) 
```

输出:

```py
GEEK before clear: set([0, 1, 4, 6])
GEEK after clear: set([])

```
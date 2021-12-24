# Python 集丢弃()功能

> 原文:[https://www.geeksforgeeks.org/python-set-discard-function/](https://www.geeksforgeeks.org/python-set-discard-function/)

discard()是从集合中移除元素的内置方法。discard()方法只接受一个参数。此方法不返回值。

**语法:**

```py
set.discard(element)
```

如果传递给 discard()的元素存在于集合中，则该元素将从集合中移除。即使传递给 discard()方法的元素不在集合中，也不会引发异常。

**示例 1:** 从集合中丢弃一个元素

## 蟒蛇 3

```py
numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9}

print(numbers)

# Deleting 5 from the set
numbers.discard(5)

# printing the resultant set
print(numbers)
```

**输出:**

> {1, 2, 3, 4, 5, 6, 7, 8, 9}
> 
> {1, 2, 3, 4, 6, 7, 8, 9}

**示例 2:** 从集合中丢弃一个元素

## 蟒蛇 3

```py
numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9}

print(numbers)

# passing an element that is not in set
numbers.discard(13)
# this will not throw any errors but set remains 
# same as before

# printing the resultant set
print("\nresultant set : ", numbers)
```

**输出:**

> {1, 2, 3, 4, 5, 6, 7, 8, 9}
> 
> 结果集:{1，2，3，4，5，6，7，8，9}

**示例 3** :从集合中丢弃一个元素

## 蟒蛇 3

```py
myset = {'a', 1, "geek", 2, 'b', 'abc', "geeksforgeeks", 8}

print(myset)

# Deleting a from the set
myset.discard("geek")

# printing the resultant set
print(myset)
```

**输出:**

> {1，2，' b '，' a '，8，' geeksforgeeks '，' abc '，' geek'}
> 
> {1， 2， 'b'， 'a'， 8， 'geeksforgeeks'， 'abc'}

**示例 4:** 从集合中丢弃一个元素

## 蟒蛇 3

```py
myset = {'a', 1, "geek", 2, 'b', 'abc', "geeksforgeeks", 8}

print(myset)

# trying to Delete geeksfrom the set which is not there
myset.discard("geeks")

# printing the resultant set
print(myset)
```

**输出:**

> {1，2，' b '，' a '，8，' geeksforgeeks '，' abc '，' geek'}
> 
> {1，2，' b '，' a '，8，' geeksforgeeks '，' abc '，' geek'}
# Python Set–remove()方法

> 原文:[https://www.geeksforgeeks.org/python-set-remove-method/](https://www.geeksforgeeks.org/python-set-remove-method/)

**Python remove()函数**是从集合中移除元素的内置方法。remove()方法只接受一个参数。

**语法**

```py
set.remove(element)
```

如果传递给 remove()的元素存在于集合中，则该元素将从集合中移除。如果传递给删除()的元素不在集合中，则[键错误](https://www.geeksforgeeks.org/built-exceptions-python/)异常将被引发。remove()方法不返回值。

**例 1:**

## 蟒蛇 3

```py
numbers = {1,2,3,4,5,6,7,8,9}
print(numbers)

# Deleting 5 from the set
numbers.remove(5)

# printing the resultant set
print(numbers)
```

**Output**

```py
{1, 2, 3, 4, 5, 6, 7, 8, 9}
{1, 2, 3, 4, 6, 7, 8, 9}
```

**例 2:**

## 蟒蛇 3

```py
numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9}

print(numbers)

# passing an element that is not in set
# this will throw an KeyError exception
try:
    numbers.remove(13)
except Exception as e:
    print("KeyError Exception raised")
    print(e, "is not present in the set")

# printing the resultant set
print("\nresultant set : ", numbers)
```

**Output**

```py
{1, 2, 3, 4, 5, 6, 7, 8, 9}
KeyError Exception raised
13 is not present in the set

resultant set :  {1, 2, 3, 4, 5, 6, 7, 8, 9}
```
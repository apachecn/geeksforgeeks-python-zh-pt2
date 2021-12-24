# Python 列表中的 Del、Remove 和 Pop 有什么区别？

> 原文:[https://www . geesforgeks . org/什么是 python 列表上的删除和弹出的区别/](https://www.geeksforgeeks.org/what-is-difference-between-del-remove-and-pop-on-python-lists/)

在 python 中 **del** 是的一个关键字， **remove()，pop()** 是内置的方法。这三种方法的目的相同但行为不同 **remove()** 方法使用 value 从列表中删除值或对象， **del** 和 **pop()** 使用 index 从列表中删除值或对象。

### 的关键字:

*del* 关键字从列表中删除任何变量、值列表。

**语法:**

```py
del list_name[index]  # To delete single value
del list_name        # To delete whole list
```

**示例:**

## 蟒蛇 3

```py
# program to demonstrate use of del keyword

# assign list
numbers = [1, 2, 3, 2, 3, 4, 5]

# use del
del numbers[2]

# display list
print(numbers)

# use del
del numbers[-1]

# display list
print(numbers)

# use del
del numbers[0]

# display list
print(numbers)
```

**输出:**

```py
[1, 2, 2, 3, 4, 5]
[1, 2, 2, 3, 4]
[2, 2, 3, 4]
```

### **移除()方法:**

*remove()* 方法从列表中删除第一个匹配值。

**语法:**

```py
list_name.remove(value)
```

**示例:**

## 蟒蛇 3

```py
# program to demonstrate use of remove() method

# assign list
numbers = [1, 2, 3, 2, 3, 4, 5]

# use remove()
numbers.remove(3)

# display list
print(numbers)

# use remove()
numbers.remove(2)

# display list
print(numbers)

# use remove()
numbers.remove(5)

# display list
print(numbers)
```

**输出:**

```py
[1, 2, 2, 3, 4, 5]
[1, 2, 3, 4, 5]
[1, 2, 3, 4]
```

### pop()方法:

像 del 这样的 pop()方法删除特定索引处的值。但是 pop()方法从列表中返回删除的值。

**语法:**

```py
list_name.pop(index)
```

**示例:**

## 蟒蛇 3

```py
# program to demonstrate use of pop() method

# assign list
numbers = [1, 2, 3, 2, 3, 4, 5]

# use remove()
numbers.pop(3)

# display list
print(numbers)

# use remove()
numbers.pop(-1)

# display list
print(numbers)

# use remove()
numbers.pop(0)

# display list
print(numbers)
```

**输出:**

```py
[1, 2, 3, 3, 4, 5]
[1, 2, 3, 3, 4]
[2, 3, 3, 4]
```

### 删除虚拟服务器删除虚拟服务器

<figure class="table">

| 

的 **del** 的

 | 

**移除()**

 | 

**【pop()**

 |
| --- | --- | --- |
| del 是一个关键字。 | 这是一种方法。 | pop()是一种方法。 |
| 要删除值，它使用索引。 | 若要删除值，此方法使用值作为参数。 | 此方法还使用索引作为要删除的参数。 |
| del 关键字不返回值。 | remove()方法不返回值。 | pop()返回删除的值。 |
| del 关键字可以从列表中删除单个值，也可以一次删除整个列表。 | 一次只从列表中删除一个值。 | 一次只从列表中删除一个值。 |
| 如果列表中不存在索引，它将引发索引错误。 | 如果列表中不存在值，它将引发值错误。 | 如果列表中不存在索引，它将引发索引错误。 |

</figure>
# Python next()方法

> 原文:[https://www.geeksforgeeks.org/python-next-method/](https://www.geeksforgeeks.org/python-next-method/)

**Python next()函数**返回迭代器的下一项。在本文中，我们将介绍 **next()语法，next()参数，next()返回。**

> **语法:** next(iter，stopdef)
> 
> **参数:**
> 
> *   **iter :** 要对其执行迭代的迭代器。
> *   **stopdef :** 到达迭代器末尾时要打印的默认值。
> 
> **返回:**返回列表中的下一个元素，如果不存在则打印默认值。如果默认值不存在，将引发停止迭代错误。

## Python next()方法示例

### **示例 1:** 演示 next()的工作

这里我们将看到 python next()循环。

## 蟒蛇 3

```
# Python code to demonstrate
# working of next()

# initializing list
list1 = [1, 2, 3, 4, 5]

# converting list to iterator
list1 = iter(list1)

print("The contents of list are : ")

# printing using next()
# using default
while (1):
    val = next(list1, 'end')
    if val == 'end':
        print('list end')
        break
    else:
        print(val)
```

**输出:**

```
The contents of list are : 
1
2
3
4
5
list end
```

### 示例 2:从迭代器中获取下一项

## 蟒蛇 3

```
list1 = [1, 2, 3, 4, 5]

# converting list to iterator
list1 = iter(list1)

print(list1)
print(next(list1))
print(next(list1))
print(next(list1))
```

**输出:**

```
<list_iterator object at 0x0000021D7C801D88>
1
2
3
```

### 示例 3:将默认值传递给下一个()

## 蟒蛇 3

```
list1 = [1, 2, 3, 4, 5]

# converting list to iterator
list1 = iter(list1)

print(list1)
print(next(list1, -1))
print(next(list1, -1))
print(next(list1, -1))
print(next(list1, -1))
print(next(list1, -1))
print(next(list1, -1))
print(next(list1, -1))
```

**输出:**

```
<list_iterator object at 0x0000021D7AE08908>
1
2
3
4
5
-1
-1
```

### 示例 6: Python next() stopiteration

## 蟒蛇 3

```
list1 = [1, 2, 3, 4, 5]

# converting list to iterator
list1 = iter(list1)

print(list1)
print(next(list1))
print(next(list1))
print(next(list1))
print(next(list1))
print(next(list1))
print(next(list1))
```

**输出:**

```
<list_iterator object at 0x0000021D7ADF55C8>
1
2
3
4
5
---------------------------------------------------------------------------
StopIteration                             Traceback (most recent call last)
<ipython-input-17-02f0e1df3bbe> in <module>
    10 print(next(list1))
    11 print(next(list1))
---> 12 print(next(list1))

StopIteration: 
```

当调用迭代器的范围之外时，它会出现停止错误，为了避免这个错误，我们将使用默认值作为参数。

### **例 5:** 性能分析

## 蟒蛇 3

```
# Python code to demonstrate
# next() vs for loop
import time

# initializing list
list1 = [1, 2, 3, 4, 5]

# keeping list2
list2 = list1

# converting list to iterator
list1 = iter(list1)

print("The contents of list are : ")

# printing using next()
# using default
start_next = time.time()
while (1):
    val = next(list1, 'end')
    if val == 'end':
        break
    else:
        print(val)
print("Time taken for next() is : " + str(time.time() - start_next))

# printing using for loop
start_for = time.time()
for i in list2:
    print(i)
print("Time taken for loop is : " + str(time.time() - start_for))
```

**输出:**

```
The contents of list are : 
1
2
3
4
5
Time taken for next() is : 5.96046447754e-06
1
2
3
4
5
Time taken for loop is : 1.90734863281e-06
```

**结果:打印列表内容时，Python next in For 循环**是比 next()更好的选择。

**应用:** next()是打印 iter 类型容器组件的实用功能。它的用法是当容器的大小未知时，或者当列表/迭代器用完时，我们需要给出提示。
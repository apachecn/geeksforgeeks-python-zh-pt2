# Python 列表复制()方法

> 原文:[https://www.geeksforgeeks.org/python-list-copy-method/](https://www.geeksforgeeks.org/python-list-copy-method/)

有时，需要重用任何对象，因此复制方法总是非常有用。Python 在其语言中提供了许多方法来实现这一点。这篇特别的文章旨在演示列表中的复制方法。由于该清单被广泛使用，因此它的副本也是必要的。

> **语法**:
> 
> list.copy()
> 
> **参数:**
> 
> copy()方法不接受任何参数
> 
> **返回:**
> 
> 返回列表的浅拷贝。浅拷贝意味着新列表中的任何修改都不会反映在原始列表中。

### **示例 1:** 演示 list.copy()的工作原理

## 蟒蛇 3

```
# Python 3 code to demonstrate
# working of list.copy()

# Initializing list
lis1 = [ 1, 2, 3, 4 ]

# Using copy() to create a shallow copy
lis2 = lis1.copy()

# Printing new list
print ("The new list created is : " + str(lis2))

# Adding new element to new list
lis2.append(5)

# Printing lists after adding new element
# No change in old list
print ("The new list after adding new element : " + str(lis2))
print ("The old list after adding new element to new list  : " + str(lis1))
```

**输出:**

```
The new list created is : [1, 2, 3, 4]
The new list after adding new element : [1, 2, 3, 4, 5]
The old list after adding new element to new list  : [1, 2, 3, 4]
```

> **注:**
> 
> 浅拷贝意味着如果我们修改任何嵌套的列表元素，当它们指向同一个引用时，更改会反映在这两个列表中。而在深度复制中，当我们在任何列表中添加一个元素时，只有那个列表被修改。当我们使用“=”运算符时，新列表引用相同的对象，因此一个列表中的任何更改(追加、移除、值更改)都会反映在两个列表中。但是当我们使用 **list.copy()** 方法时，对一个列表所做的更改或者除了嵌套元素(如列表中的列表)之外没有反映在其他列表上的更改，这里我们应该使用复制模块中的 **copy.deepcopy()** 来避免这个问题。请参考本文 [**深抄 vs 浅抄**](https://www.geeksforgeeks.org/copy-python-deep-copy-shallow-copy/) **。**
> 
> *   **深度复制技术:**
>     *   使用 copy.deepcopy()
> *   **浅复制技术:**
>     *   使用 copy.copy()
>     *   使用 list.copy()
>     *   使用切片

### **例 2:** 浅、深复制演示技术

## 蟒蛇 3

```
# Python 3 code to demonstrate
# techniques of deep and shallow copy
import copy

# Initializing list
list1 = [ 1, [2, 3] , 4 ]

# all changes are reflected
list2 = list1

# shallow copy - changes to
# nested list is reflected,
# same as copy.copy(), slicing

list3 = list1.copy()

# deep copy - no change is reflected
list4 = copy.deepcopy(list1)

list1.append(5)
list1[1][1] = 999

print("list 1 after modification:\n", list1)
print("list 2 after modification:\n", list2)
print("list 3 after modification:\n", list3)
print("list 4 after modification:\n", list4)
```

**输出:**

```
list 1 after modification:
 [1, [2, 999], 4, 5]
list 2 after modification:
 [1, [2, 999], 4, 5]
list 3 after modification:
 [1, [2, 999], 4]
list 4 after modification:
 [1, [2, 3], 4]
```
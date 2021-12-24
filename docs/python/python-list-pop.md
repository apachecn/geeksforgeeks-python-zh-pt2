# Python list | pop()

> 原文:[https://www.geeksforgeeks.org/python-list-pop/](https://www.geeksforgeeks.org/python-list-pop/)

Python 列表 ***pop()*** 是 Python 中的一个内置函数，它从[列表](https://www.geeksforgeeks.org/python-list/)或给定的索引值中移除并返回最后一个值。

> **语法:**
> 
> list_name.pop(索引)
> 
> **参数:**
> 
> *   **索引** ( *可选*)–索引处的值被弹出并移除。如果没有给出索引，那么最后一个元素被弹出并移除。
> 
> **返回:**列表中的最后一个值或给定的索引值。
> 
> **异常:**当索引超出范围时，返回 IndexError。

### **例 1:使用 pop()方法**

## 蟒蛇 3

```
# Python3 program for pop() method

list1 = [ 1, 2, 3, 4, 5, 6 ]

# Pops and removes the last element from the list
print(list1.pop())

# Print list after removing last element
print("New List after pop : ", list1, "\n")

list2 = [1, 2, 3, ('cat', 'bat'), 4]

# Pop last three element
print(list2.pop())
print(list2.pop())
print(list2.pop())

# Print list
print("New List after pop : ", list2, "\n")
```

**输出:**

```
6
New List after pop :  [1, 2, 3, 4, 5] 

4
('cat', 'bat')
3
New List after pop :  [1, 2] 
```

### **例 2**

## 蟒蛇 3

```
# Python3 program showing pop() method
# and remaining list after each pop

list1 = [ 1, 2, 3, 4, 5, 6 ]

# Pops and removes the last
# element from the list
print(list1.pop(), list1)

# Pops and removes the 0th index
# element from the list
print(list1.pop(0), list1)
```

**输出:**

```
6 [1, 2, 3, 4, 5]
1 [2, 3, 4, 5]
```

### **示例 3:** 演示索引错误

## 蟒蛇 3

```
# Python3 program for error in pop() method

list1 = [ 1, 2, 3, 4, 5, 6 ]
print(list1.pop(8))
```

**输出:**

```
Traceback (most recent call last):
  File "/home/1875538d94d5aecde6edea47b57a2212.py", line 5, in 
    print(list1.pop(8))
IndexError: pop index out of range
```

### **例 4:实例**

水果列表包含*水果名称*和表示其水果的*属性*。另一个消费清单有两个项目*果汁*和*吃*。借助 pop()和 [append()](https://www.geeksforgeeks.org/append-extend-python/) 我们可以做一些有趣的事情。

## 蟒蛇 3

```
# Python3 program demonstrating
# practical use of list pop()

fruit = [['Orange','Fruit'],['Banana','Fruit'], ['Mango', 'Fruit']]
consume = ['Juice', 'Eat']
possible = []

# Iterating item in list fruit
for item in fruit :

    # Inerating use in list consume
    for use in consume :

        item.append(use)
        possible.append(item[:])
        item.pop(-1)
print(possible)
```

**输出:**

```
[['Orange', 'Fruit', 'Juice'], ['Orange', 'Fruit', 'Eat'],
 ['Banana', 'Fruit', 'Juice'], ['Banana', 'Fruit', 'Eat'],
 ['Mango', 'Fruit', 'Juice'], ['Mango', 'Fruit', 'Eat']]
```
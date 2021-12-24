# Python 程序交换列表中的两个元素

> 原文:[https://www . geesforgeks . org/python-程序到交换-列表中的两个元素/](https://www.geeksforgeeks.org/python-program-to-swap-two-elements-in-a-list/)

给定 Python 中的一个列表并提供元素的位置，编写一个程序来交换列表中的两个元素。
**例:**

```py
Input : List = [23, 65, 19, 90], pos1 = 1, pos2 = 3
Output : [19, 65, 23, 90]

Input : List = [1, 2, 3, 4, 5], pos1 = 2, pos2 = 5
Output : [1, 5, 3, 4, 2]
```

**方法#1:** 简单互换，使用逗号赋值
由于元素的位置是已知的，我们可以简单地互换元素的位置。

## 蟒蛇 3

```py
# Python3 program to swap elements
# at given positions

# Swap function
def swapPositions(list, pos1, pos2):

    list[pos1], list[pos2] = list[pos2], list[pos1]
    return list

# Driver function
List = [23, 65, 19, 90]
pos1, pos2  = 1, 3

print(swapPositions(List, pos1-1, pos2-1))
```

**输出:**

```py
[19, 65, 23, 90]
```

**方法 2 :** 使用内置的 list.pop()函数
将元素弹出到 *pos1* 并将其存储在变量中。同样，在 *pos2* 弹出元素，并将其存储在另一个变量中。现在在彼此的原始位置插入两个弹出的元素。

## 蟒蛇 3

```py
# Python3 program to swap elements
# at given positions

# Swap function
def swapPositions(list, pos1, pos2):

    # popping both the elements from list
    first_ele = list.pop(pos1)  
    second_ele = list.pop(pos2-1)

    # inserting in each others positions
    list.insert(pos1, second_ele) 
    list.insert(pos2, first_ele) 

    return list

# Driver function
List = [23, 65, 19, 90]
pos1, pos2  = 1, 3

print(swapPositions(List, pos1-1, pos2-1))
```

**输出:**

```py
[19, 65, 23, 90]
```

**方法#3 :** 使用元组变量
将位于 *pos1* 和 *pos2* 的元素作为一对存储在元组变量中，比如说*得到*。用列表中的 *pos2* 和 *pos1* 位置打开这些元素。现在，列表中的两个位置都被交换了。

## 蟒蛇 3

```py
# Python3 program to swap elements at
# given positions

# Swap function
def swapPositions(list, pos1, pos2):

    # Storing the two elements
    # as a pair in a tuple variable get
    get = list[pos1], list[pos2]

    # unpacking those elements
    list[pos2], list[pos1] = get

    return list

# Driver Code
List = [23, 65, 19, 90]

pos1, pos2  = 1, 3
print(swapPositions(List, pos1-1, pos2-1))
```

**输出:**

```py
[19, 65, 23, 90]
```
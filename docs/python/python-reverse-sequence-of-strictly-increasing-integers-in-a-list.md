# Python |列表中严格递增整数的逆序

> 原文:[https://www . geesforgeks . org/python-列表中严格递增整数的反向序列/](https://www.geeksforgeeks.org/python-reverse-sequence-of-strictly-increasing-integers-in-a-list/)

给定一个整数列表，编写一个 Python 程序来反转给定列表中块连续递增的顺序。

**示例:**

```py
Input : [0, 1, 9, 8, 7, 5, 3, 14]
Output : [9, 1, 0, 8, 7, 5, 14, 3]
Explanation: There are two chunks of strictly
             increasing elements (0, 1, 9) and (3, 14). 

Input : [-5, -3, 0, 1, 3, 5, -2, -12]
Output : [5, 3, 1, 0, -3, -5, -2, -12]
Explanation: Only one chunk of strictly increasing 
             elements exists i.e. (-5, -3, 0, 1, 3, 5).

```

**方法#1 :** 天真(使用扩展切片)

解决给定问题的一种简单方法是使用扩展切片。我们用空列表初始化两个变量“res”(存储最终输出)和 block(存储递增整数块)。现在使用 for 循环，每次我们检查当前元素是否小于块的最后一个元素。如果是，使用扩展切片(块[:-1])和干净块(块[:] = [i])将反向块添加到“res”。否则，只需将元素追加到“block”中。最后，通过反转块来扩展“res”并将其输出。

```py
# Python3 program to Reverse order 
# of incrementing integers in list

def reverseOrder(lst):
    res = [] 
    block = []
    for i in lst:

        # check if the current element is less 
        # than the last element of block 
        if block and i < block[-1]:

            # add reversed chunk to 'res'
            res.extend(block[::-1]) 
            block[:] = [i]      
        else:

            # append the element to 'block'
            block.append(i)

    # extend 'res' by reversing block    
    res.extend(block[::-1])
    return(res)

# Driver code
lst = [0, 1, 9, 8, 7, 5, 3, 14]
print(reverseOrder(lst))
```

**Output:**

```py
[9, 1, 0, 8, 7, 5, 14, 3]

```

**方法 2 :** 使用列表理解

解决上述问题的有效方法是使用列表理解。它首先找出递增整数开始的所有位置，并将它们存储在变量“break_”中。在此之后，所有的块都被反转，并以子列表的形式进行管理，这些子列表又存储在“块”中。最后，解压并返回“block”。

```py
# Python3 program to Reverse order 
# of incrementing integers in list

def reverseOrder(lst):
    break_ = [0] + [i for i in range(1, len(lst)) 
    if lst[i-1] > lst[i]] + [len(lst)]

    block =[list(reversed(lst[i:j])) 
    for i, j in zip(break_[:-1], break_[1:])]

    return(sum(block, [])) 

# Driver code
lst = [0, 1, 9, 8, 7, 5, 3, 14]
print(reverseOrder(lst))
```

**Output:**

```py
[9, 1, 0, 8, 7, 5, 14, 3]

```
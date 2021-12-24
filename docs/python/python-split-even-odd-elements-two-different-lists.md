# Python |将偶数和奇数元素拆分成两个不同的列表

> 原文:[https://www . geesforgeks . org/python-split-偶数-奇数-元素-两个不同-列表/](https://www.geeksforgeeks.org/python-split-even-odd-elements-two-different-lists/)

在这个程序中，一个列表接受奇数和偶数元素的混合，根据元素是偶数还是奇数，它被分成两个不同的列表。

示例:

```
Input : [8, 12, 15, 9, 3, 11, 26, 23]
Output : Even lists: [8, 12, 26]
         Odd lists: [15, 9, 3, 11, 23]

Input : [2, 5, 13, 17, 51, 62, 73, 84, 95]
Output : Even lists: [2, 62, 84]
         Odd lists: [5, 13, 17, 51, 73, 95]

```

```
# Python code to split into even and odd lists
# Function to split
def Split(mix):
    ev_li = []
    od_li = []
    for i in mix:
        if (i % 2 == 0):
            ev_li.append(i)
        else:
            od_li.append(i)
    print("Even lists:", ev_li)
    print("Odd lists:", od_li)

# Driver Code
mix = [2, 5, 13, 17, 51, 62, 73, 84, 95]
Split(mix)
```

输出:

```
Even lists: [2, 62, 84]
Odd lists: [5, 13, 17, 51, 73, 95]

```

 **备选较短方案:**

```
def Split(mix):
    ev_li = [ele for ele in li_in if ele%2 ==0]
    od_li = [ele for ele in li_in if ele%2 !=0]
    print("Even lists:", ev_li)
    print("Odd lists:", od_li)

# Driver Code
mix = [2, 5, 13, 17, 51, 62, 73, 84, 95]
Split(mix)
```

输出:

```
Even lists: [2, 62, 84]
Odd lists: [5, 13, 17, 51, 73, 95]

```
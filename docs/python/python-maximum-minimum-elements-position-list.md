# Python |列表中最大和最小元素的位置

> 原文:[https://www . geesforgeks . org/python-最大-最小-元素-位置-列表/](https://www.geeksforgeeks.org/python-maximum-minimum-elements-position-list/)

给定一个 N 个整数的列表，找到列表中最大和最小元素的位置。

**示例:**

```
Input :  3, 4, 1, 3, 4, 5
Output :  The maximum is at position 6
          The minimum is at position 3

```

**天真的方法**是遍历列表，跟踪最小值和最大值以及它们的索引。我们必须为最小值做 N 次比较，同时为最大值做 N 次比较。
下面是天真方法的实现。

```
#Naive approach
#to find index of maximum and
#minimum element in the array.
gfg_list=[8,1,7,10,5]
#min and max indexes are taken 1st element 
#In some cases list might be a single element
min_ele,max_ele=gfg_list[0],gfg_list[0] 
for i in range(1,len(gfg_list)):
    if gfg_list[i]<min_ele:
        min_ele=gfg_list[i]
    if gfg_list[i]>max_ele:
        max_ele=gfg_list[i]
print('Minimum Element in the list',gfg_list,'is',min_ele)
print('Maximum Element in the list',gfg_list,'is',max_ele)
```

**Output:**

```
Minimum Element in the list [8, 1, 7, 10, 5] is 1
Maximum Element in the list [8, 1, 7, 10, 5] is 10

```

**Python 内置函数**允许我们在一行中找到它，我们可以使用 **[min()](https://www.geeksforgeeks.org/list-methods-python/)** 函数找到列表中的最小值，然后使用 **[index()](https://www.geeksforgeeks.org/list-methods-python/)** 函数找出该最小元素的索引。同样，我们也可以使用 **[max()](https://www.geeksforgeeks.org/list-methods-python/)** 函数找出最大元素，然后使用 python 中的 index()内置函数找出最大元素的索引。
 **注意:** index()返回一个元素多次出现时第一次出现的索引。因此，如果最大值(或最小值)出现多次，则返回第一次出现的值。

下面是上述方法的实现:

```
# function to find minimum and maximum position in list
def minimum(a, n):

    # inbuilt function to find the position of minimum 
    minpos = a.index(min(a))

    # inbuilt function to find the position of maximum 
    maxpos = a.index(max(a)) 

    # printing the position 
    print "The maximum is at position", maxpos + 1  
    print "The minimum is at position", minpos + 1

# driver code
a = [3, 4, 1, 3, 4, 5] 
minimum(a, len(a))
```

**Output:**

```
The maximum is at position 6
The minimum is at position 3

```
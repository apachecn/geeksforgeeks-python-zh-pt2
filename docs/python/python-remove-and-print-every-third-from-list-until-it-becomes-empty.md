# Python |从列表中删除并打印三分之一，直到它变成空的

> 原文:[https://www . geesforgeks . org/python-从列表中删除并打印每三分之一，直到它变成空的/](https://www.geeksforgeeks.org/python-remove-and-print-every-third-from-list-until-it-becomes-empty/)

给定一个数字列表，您的任务是删除并打印数字列表中的每三个数字，直到列表变空。
示例:

> 输入:[10，20，30，40，50，60，70，80，90]
> 输出:30 60 90 40 80 50 20 70 10
> 解释:
> 遇到的第一个第三个元素是 30，30 之后我们从 40 开始计数下一个第三个元素是 60，之后遇到 90。然后，对于下一个第三个元素(40)，计数再次从 10 开始。以与我们在 40 岁之后得到下一个第三个元素之前相同的方式进行。重复这个过程，直到列表变空。
> 
> 输入:[1，2，3，4]
> 输出:3 2 4 1
> 解释:
> 遇到的第一个第三个元素是 3，3 之后我们从 4 开始计数下一个第三个元素是 2。然后，对于下一个第三元素，计数再次从 4 开始，第三元素本身是 4，最后打印最后一个元素 1。

**接近**列表的索引从 0 开始，第一个第三个元素将位于位置 2。遍历直到列表变成空的，每次找到下一个第三个元素的索引并打印它的相应值。打印后减少列表的长度。

```
# Python program to remove to every third
# element until list becomes empty
def removeThirdNumber(int_list):

    # list starts with
    # 0 index
    pos = 3 - 1
    index = 0
    len_list = (len(int_list))

    # breaks out once the
    # list becomes empty
    while len_list > 0: 

        index = (pos + index) % len_list

        # removes and prints the required
        # element
        print(int_list.pop(index)) 
        len_list -= 1

# Driver code
nums = [1, 2, 3, 4] 
removeThirdNumber(nums)
```

输出:

```
3
2
4
1

```
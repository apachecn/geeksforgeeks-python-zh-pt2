# Python |列表中的 Shift 子列表

> 原文:[https://www.geeksforgeeks.org/python-shift-sublist-in-list/](https://www.geeksforgeeks.org/python-shift-sublist-in-list/)

有时，在使用列表时，我们会遇到一个问题，需要将一些子列表转移到同一个子列表中的所需索引。这个问题可能发生在日常编程中。让我们讨论执行这项任务的某些方法。

**方法#1:使用`insert() + pop()` +循环**
上述功能的组合可用于执行特定任务。 `pop`功能可以删除子列表，`insert`功能可以插入子列表。循环中的单次迭代中的每个元素都会发生这种情况。

```py
# Python3 code to demonstrate working of
# Shift sublist in list
# Using insert() + pop() + loop

# function to perform the task 
def shift_sublist(test_list, strt_idx, no_ele, shft_idx):
    for ele in range(no_ele):
        test_list.insert(shft_idx + 1, test_list.pop(strt_idx))
    return test_list

# initializing list
test_list = [4, 5, 6, 7, 3, 8, 10, 1, 12, 15, 16]

# printing original list
print("The original list is : " +  str(test_list))

# Using insert() + pop() + loop
# Shift sublist in list
res = shift_sublist(test_list, 2, 3, 6)

# Printing result
print("The list after shift of sublist : " +  str(res))
```

**Output :**

> 原列表为:【4、5、6、7、3、8、10、1、12、15、16】
> 子列表移位后的列表:【4、5、8、10、1、6、7、3、12、15、16】
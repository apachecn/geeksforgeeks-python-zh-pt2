# Python 程序从列表的每个元素中删除一个特定的数字

> 原文:[https://www . geesforgeks . org/python-program-to-remove-从列表的每个元素中删除特定的数字/](https://www.geeksforgeeks.org/python-program-to-remove-a-specific-digit-from-every-element-of-the-list/)

给定元素列表，这里的任务是编写一个 Python 程序，可以从每个元素中删除所有特定数字的存在，然后返回结果列表。

**示例:**

> **输入** : test_list = [333，893，1948，34，2346]，K = 3
> **输出** : [，89，1948，4，246]
> **解释**:3 的所有出现都被移除。
> 
> **输入**:test _ list =【345，893，1948，34，2346】，K = 5
> **输出**:【34，893，1948，34，2346】
> **解释**:5 的所有出现都被移除。

**方法 1 :** 使用[循环](https://www.geeksforgeeks.org/python-for-loops/)、 [str()](https://www.geeksforgeeks.org/python-str-function/) 和[连接()](https://www.geeksforgeeks.org/join-function-python/)

在这种情况下，我们通过将元素转换为字符串并检查每个数字并在连接时忽略以获得新元素来执行重组元素的任务。最后，使用 int()将每个元素转换为整数。

**示例:**

## 蟒蛇 3

```
# initializing list
test_list = [345, 893, 1948, 34, 2346]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

res = []
for ele in test_list:

    # joining using join(),
    if list(set(str(ele)))[0] == str(K) and len(set(str(ele))) == 1:
        res.append('')
    else:
        res.append(int(''.join([el for el in str(ele) if int(el) != K])))

# printing result
print("Modified List : " + str(res))
```

**输出:**

> 最初的名单是:[345，893，1948，34，2346]
> 
> 修改列表:[45，89，1948，4，246]

**方法二:**使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)、 [int(](https://www.geeksforgeeks.org/python-int-function/) )、 [str()](https://www.geeksforgeeks.org/python-str-function/) 和 [join()](https://www.geeksforgeeks.org/join-function-python/)

与上述方法类似，连接使用 join()完成，相互转换使用 int()和 str()执行。

**示例:**

## 蟒蛇 3

```
# initializing list
test_list = [345, 893, 1948, 34, 2346]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# list comprehension performing task as one liner
res = ['' if list(set(str(ele)))[0] == str(K) and len(set(str(ele))) == 1 else int(
    ''.join([el for el in str(ele) if int(el) != K])) for ele in test_list]

# printing result
print("Modified List : " + str(res))
```

**输出:**

> 最初的名单是:[345，893，1948，34，2346]
> 
> 修改列表:[45，89，1948，4，246]
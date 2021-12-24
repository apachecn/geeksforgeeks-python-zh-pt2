# Python |计算元组列表中重复项的程序

> 原文:[https://www . geesforgeks . org/python-程序到计数-元组列表中的重复项/](https://www.geeksforgeeks.org/python-program-to-count-duplicates-in-a-list-of-tuples/)

给定一个元组列表，编写一个 Python 程序来检查列表中的元素是否有重复。如果存在重复，打印每个重复元组的出现次数，否则打印“无重复”。

**示例:**

> **输入:** [('a '，' e ')，(' b '，' x ')，(' b '，' x ')，(' a '，' e '，(' b '，' x')]
> **输出:**
> ('a '，' e ')–2
> (' b '，' x ')–3
> 
> **输入:** [(0，5)，(6，9)，(0，8)]
> **输出:**无重复

让我们看看在元组列表中计数重复项的各种方法。

**方法#1 :** 简单方法

这种方法使用两个循环遍历列表元素，并检查每个元素的第一个元素和第二个元素是否与任何其他元组匹配。

```
# Python3 code to convert tuple 
# into string
def count(listOfTuple):

    flag = False

    # To append Duplicate elements in list
    coll_list = []  
    coll_cnt = 0
    for t in listOfTuple:

        # To check if Duplicate exist
        if t in coll_list:  
            flag = True
            continue

        else:
            coll_cnt = 0
            for b in listOfTuple:
                if b[0] == t[0] and b[1] == t[1]:
                    coll_cnt = coll_cnt + 1

            # To print count if Duplicate of element exist
            if(coll_cnt > 1): 
                print(t, "-", coll_cnt)
            coll_list.append(t)

    if flag == False:
        print("No Duplicates")

# Driver code
print("Test Case 1:")
listOfTuple = [('a', 'e'), ('b', 'x'), ('b', 'x'), 
               ('a', 'e'), ('b', 'x')] 

count(listOfTuple)

print("Test Case 2:")
listOfTuple = [(0, 5), (6, 9), (0, 8)]
count(listOfTuple)
```

**Output:**

```
Test Case 1:
('a', 'e') - 2
('b', 'x') - 3

Test Case 2:
No Duplicates

```

时间复杂度–O(n)<sup>2</sup>

**方法 2 :** 使用计数器

计数器是集合模块中包含的容器。这是一个无序的集合，其中元素及其各自的计数被存储为字典。

```
# Python3 code to convert tuple 
# into string
import collections

def count(listOfTuple):

    flag = False
    val = collections.Counter(listOfTuple)
    uniqueList = list(set(listOfTuple))

    for i in uniqueList:
        if val[i]>= 2:
            flag = True
            print(i, "-", val[i])

    if flag == False:
        print("Duplicate doesn't exist")

# Driver code
listOfTuple = [('a', 'e'), ('b', 'x'), ('b', 'x'), 
               ('a', 'e'), ('b', 'x')] 
count(listOfTuple)
```

**Output:**

```
('b', 'x') - 3
('a', 'e') - 2

```

时间复杂性–O(n)

**使用另一个格言接近#3 :**

你可以做一个字典，说`count_map`，把每个元组的计数作为值存储起来。

```
# Python3 code to convert tuple 
# into string
def count(listOfTuple):

    count_map = {}
    for i in listOfTuple:
        count_map[i] = count_map.get(i, 0) +1
    print(count_map)

# Driver code
print("Test Case 1:")
listOfTuple = [('a', 'e'), ('b', 'x'), ('b', 'x'), 
               ('a', 'e'), ('b', 'x')] 

count(listOfTuple)
```

**Output:**

```
Test Case 1:
{('a', 'e'): 2, ('b', 'x'): 3}

```

时间复杂性–O(n)
# Python |测试列表元素相似度

> 原文:[https://www . geesforgeks . org/python-test-list-element-similarity/](https://www.geeksforgeeks.org/python-test-list-element-similarity/)

给定一个列表，您的任务是确定该列表是 K %相同的，即元素被填充的次数超过 K %。

下面给出了几个解决任务的方法。
**方法#1 使用集合。柜台**

```
# Python3 code to demonstrate
# to check whether the list
# K percent same or not
from collections import Counter

# initializing list
ini_list1 = [1, 2, 3, 1, 1, 1, 1, 1, 3, 2]

# printing initial list
print ("Initial list", ini_list1)

# initializing K
K = 60

# code to check whether list is K % same or not
i, freq = Counter(ini_list1).most_common(1)[0]

if len(ini_list1)*(K / 100) <= freq:
    print("True")
else:
    print("False")
```

**输出:**

```
Initial list [1, 2, 3, 1, 1, 1, 1, 1, 3, 2] 
True

```

**方法 2:使用字典及其值**

```
# Python3 code to demonstrate
# to check whether the list
# K percent same or not
from collections import Counter, defaultdict

# initializing list
ini_list1 = [1, 2, 3, 1, 1, 1, 1, 1, 3, 2]

# printing initial list
print ("Initial list", ini_list1)

# initializing K
K = 60

# code to check whether list is K % same or not
freq = defaultdict(int)
for x in ini_list1:
    freq[x] += 1
freq = freq.values()
if max(freq) >= (K / 100) * sum(freq):
    print ("True")
else:
    print ("False")
```

**输出:**

```
initial list [1, 2, 3, 1, 1, 1, 1, 1, 1, 1]
True

```
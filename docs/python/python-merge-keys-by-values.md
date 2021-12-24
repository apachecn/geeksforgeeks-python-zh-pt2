# Python–按值合并键

> 原文:[https://www.geeksforgeeks.org/python-merge-keys-by-values/](https://www.geeksforgeeks.org/python-merge-keys-by-values/)

给定一个字典，合并键以映射到公共值。

**示例:**

> **输入** : test_dict = {1:6，8:1，9:3，10:3，12:6，4:9，2:3}
> **输出** : {'1-12': 6，' 2-9-10': 3，' 4': 9，' 8': 1}
> **解释**:所有相似的值键合并。
> 
> **输入** : test_dict = {1:6，8:1，9:3，4:9，2:3}
> **输出** : {'1': 6，' 2-9': 3，' 4': 9，' 8 ':1 }
> **:所有相似值键合并。**

****方法:使用**[**default dict()**](https://www.geeksforgeeks.org/defaultdict-in-python/)**+循环****

**该任务分两步执行，第一步，将所有值分组并存储关键字，第二步，将合并的关键字映射到公共值。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of
# Merge keys by values
# Using defaultdict() + loop
from collections import defaultdict

# initializing dictionary
test_dict = {1: 6, 8: 1, 9: 3, 10: 3, 12: 6, 4: 9, 2: 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# grouping values
temp = defaultdict(list)
for key, val in sorted(test_dict.items()):
    temp[val].append(key)

res = dict()
# merge keys
for key in temp:
    res['-'.join([str(ele) for ele in temp[key]])] = key

# printing result
print("The required result : " + str(res))
```

****输出:****

> **原始字典为:{1: 6，8: 1，9: 3，10: 3，12: 6，4: 9，2: 3}
> 所需结果:{'1-12': 6，' 2-9-10': 3，' 4': 9，' 8': 1}**
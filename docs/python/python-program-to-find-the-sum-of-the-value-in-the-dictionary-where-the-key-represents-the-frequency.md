# Python 程序查找字典中值的和，其中键代表频率

> 原文:[https://www . geesforgeks . org/python-program-to-find-the-sum-in-dictionary-key-where-表示频率/](https://www.geeksforgeeks.org/python-program-to-find-the-sum-of-the-value-in-the-dictionary-where-the-key-represents-the-frequency/)

给定一个带有值列表的字典，其中键代表频率，计算值列表中每个值的总出现次数。

> **输入** : test_dict = {70 : [7，4，6]，50 : [6，8，5，2]}
> **输出** : {7: 70，4: 70，6: 120，8: 50，5: 50，2: 50}
> **解释** : 6 出现在两个键中，因此 70 + 50 = 120，赋给 6。
> 
> **输入** : test_dict = {70 : [7，4]，50 : [6，8，5，2]}
> **输出** : {7: 70，4: 70，6: 50，8: 50，5: 50，2: 50}
> **解释** : 6 现在只出现在 50 键，因此只分配了 50。

**方法:reduce()+Counter()+lambda+_ _ add _ _**

这是执行这项任务的方式。在这种情况下，Counter()用于计算每个值的频率，使用 __add__ 完成与键的求和，使用 reduce()将每个键的所有值相加。map()用于将 Counter 的逻辑扩展到值列表中的每个值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Frequency Key Values Summation
# Using reduce() + Counter() + lambda + __add__
from functools import reduce
from collections import Counter

# initializing dictionary
test_dict = {70 : [7, 4, 6], 
             100 : [8, 9, 5], 
             200 : [2, 5, 3, 7], 
             50 : [6, 8, 5, 2]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Counter() used to get values mapped with keys 
# __add__ used to add key with values.
res = reduce(Counter.__add__, map(lambda sub: Counter({ele : sub[0] for ele in sub[1]}), 
                    test_dict.items()) )
# printing result 
print("Extracted Summation dictionary : " + str(dict(res))) 
```

**输出:**

> 原始字典为:{70: [7，4，6]，100: [8，9，5]，200: [2，5，3，7]，50: [6，8，5，2]}
> 提取求和字典:{7: 270，4: 70，6: 120，8: 150，9: 100，5: 350，2: 250，3: 200}
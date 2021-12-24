# Python–列表中最大出现的子串

> 原文:[https://www . geesforgeks . org/python-最大出现次数-列表中的子串/](https://www.geeksforgeeks.org/python-maximum-occurring-substring-from-list/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，需要从字符串列表中检查最大出现的子字符串。这可以在生物学中的 DNA 测序和其他应用中得到应用。让我们讨论执行这项任务的特定方式。
**方法:使用 regex()+group by()+max()+lambda**
以上功能的组合可以用来解决这个特殊的问题。在这种情况下，我们首先使用正则函数提取序列。然后使用 groupby()执行计数器分组。最后一步是提取最大值，这是使用 max()和 lambda 函数完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum occurring Substring from list
# Using regex() + groupby() + max() + lambda
import re
import itertools

# initializing string
test_str = "gfghsisbjknlmkesbestgfgsdcngfgcsdjnisdjnlbestdjsklgfgcdsbestbnjdsgfgdbhisbhsbestdkgfgb"
test_list = ['gfg', 'is', 'best']

# printing original string and list
print("The original string is : " + test_str)
print("The original list is : " + str(test_list))

# Maximum occurring Substring from list
# Using regex() + groupby() + max() + lambda
seqs = re.findall(str.join('|', test_list), test_str)
grps = [(key, len(list(j))) for key, j in itertools.groupby(seqs)]
res = max(grps, key = lambda ele : ele[1])

# printing result
print("Maximum frequency substring : " + str(res[0]))
```

**Output : **

```
The original string is : gfghsisbjknlmkesbestgfgsdcngfgcsdjnisdjnlbestdjsklgfgcdsbestbnjdsgfgdbhisbhsbestdkgfgb
The original list is : ['gfg', 'is', 'best']
Maximum frequency substring : gfg
```
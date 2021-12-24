# Python |使用计数器的具有不同元素的子集的最小数量

> 原文:[https://www . geesforgeks . org/python-最小数量-子集-不同元素-使用-计数器/](https://www.geeksforgeeks.org/python-minimum-number-subsets-distinct-elements-using-counter/)

给你一个 n 元素数组。您必须从数组中创建子集，这样子集就不会包含重复的元素。找出可能的最小子集数。

示例:

```
Input : arr[] = {1, 2, 3, 4}
Output :1
Explanation : A single subset can contains all 
values and all values are distinct

Input : arr[] = {1, 2, 3, 3}
Output : 2
Explanation : We need to create two subsets
{1, 2, 3} and {3} [or {1, 3} and {2, 3}] such
that both subsets have distinct elements.

```

对于这个问题我们已经有了解决方案，请参考[具有不同元素的子集的最小数量](https://www.geeksforgeeks.org/minimum-number-subsets-distinct-elements/)链接。我们将使用 [Counter(iterable)](https://www.geeksforgeeks.org/counters-in-python-set-1/) 方法在 python 中快速解决这个问题。方法很简单，计算数组中每个元素的频率，并打印最大频率的值，因为我们希望每个子集不同，并且我们必须将任何重复的元素放在不同的子集中，所以要获得最小数量的子集，我们应该至少有**个最大频率数量的子集**。

```
# Python program to find Minimum number of 
# subsets with distinct elements using Counter

# function to find Minimum number of subsets 
# with distinct elements
from collections import Counter

def minSubsets(input):

     # calculate frequency of each element
     freqDict = Counter(input)

     # get list of all frequency values
     # print maximum from it 
     print (max(freqDict.values()))

# Driver program
if __name__ == "__main__":
    input = [1, 2, 3, 3]
    minSubsets(input)
```

输出:

```
2

```
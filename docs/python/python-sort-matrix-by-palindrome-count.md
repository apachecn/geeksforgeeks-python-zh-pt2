# Python–按回文计数对矩阵进行排序

> 原文:[https://www . geeksforgeeks . org/python-sort-matrix-by-回文-count/](https://www.geeksforgeeks.org/python-sort-matrix-by-palindrome-count/)

给定一个字符串矩阵，按回文字符串计数对每行进行排序。

> **输入**:test _ list =[[“Nitin”、“meem”、“极客”]、[“peep”]、[“gfg”、“is”、“best”]、[“sees”、“level”、“mom”、“noon”]]
> **输出**:[[[“peep”]、[“gfg”、“is”、“best”]、[“Nitin”、“meem”、“极客”]、[“sees”、“level”、“mom”、“noon”]
> **解释** : 1 = 1 < 2
> 
> **输入**:test _ list =[[“Nitin”、“meem”、“极客”]、[“peep”]、[“sees”、“level”、“mom”、“noon”]]
> **输出**:[[“peep”]、[“Nitin”、“meem”、“极客”]、[“sees”、“level”、“mom”、“noon”]
> **解释** : 1 < 2 < 4 为回文计数顺序。

**方法#1:使用** [**反转()**](https://www.geeksforgeeks.org/python-reversed-function/)**+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+sort()**

在本文中，我们使用 sort()执行就地排序，长度计算和回文检查使用 reversed()完成。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Matrix by Palindrome count
# Using reversed() + len() + sort()

# get palin
def get_palin_freq(row):

    # returning length
    return len([sub for sub in row if ''.join(list(reversed(sub))) == sub])

# initializing list
test_list = [["nitin", "meem", "geeks"], ["peep"],
             ["gfg", "is", "best"], 
             ["sees", "level", "mom", "noon"]]

# printing original list
print("The original list is : " + str(test_list))

# performing sort
test_list.sort(key=get_palin_freq)

# printing result
print("Sorted rows : " + str(test_list))
```

**输出:**

> 原始列表为:[['nitin '，' meem '，' geeks']，['gfg '，' is '，' best']，['sees '，' level '，' mom '，' noon']]
> 排序行:[['peep '，['gfg '，' is '，' best']，['nitin '，' meem '，' geeks']，['sees '，' level '，' mom '，' noon']

**方法 2:使用排序()+ len() + reversed()**

与上面的方法类似，被排序的差异()与 lambda 函数一起使用，在没有外部函数调用的情况下执行单行任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Matrix by Palindrome count
# Using sorted() + len() + reversed()

# initializing list
test_list = [["nitin", "meem", "geeks"], ["peep"],
             ["gfg", "is", "best"], ["sees", "level", "mom", "noon"]]

# printing original list
print("The original list is : " + str(test_list))

# performing sort
# sorted() and lambda used to get 1 sentence approach
res = sorted(test_list, key=lambda row: len(
    [sub for sub in row if ''.join(list(reversed(sub))) == sub]))

# printing result
print("Sorted rows : " + str(res))
```

**输出:**

> 原始列表为:[['nitin '，' meem '，' geeks']，['gfg '，' is '，' best']，['sees '，' level '，' mom '，' noon']]排序行:[['peep '，['gfg '，' is '，' best']，['nitin '，' meem '，' geeks']，['sees '，' level '，' mom '，' noon']
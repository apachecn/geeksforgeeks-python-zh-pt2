# Python 程序检查所有字符串元素的字符是否按词法顺序排列

> 原文:[https://www . geesforgeks . org/python-program-to-check-所有字符串元素的字符是否按词法顺序排列/](https://www.geeksforgeeks.org/python-program-to-check-whether-characters-of-all-string-elements-are-in-lexical-order-or-not/)

给定一个包含字符串元素的列表，任务是编写一个 Python 程序，如果所有列表元素都被排序，则返回 True。这里需要注意的是，我们将字符串列表元素的字符与同一列表元素的其他字符进行比较，而不是字符串元素之间的比较。

**示例:**

> **输入:** test_list = [“凹痕”、“翻牌”、“最多”、“分”]
> 
> **输出:**真
> 
> **说明:**所有字符排序。
> 
> **输入:** test_list = [“凹痕”、“翻板”、“薄雾”、“中心”]
> 
> **输出:**假
> 
> **解说:** m >我在雾中，遂乱阵脚。所以，返回假。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/python-for-loops/) *和* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)

在这种情况下，我们对每个字符串进行迭代，并使用 sorted()测试是否所有的字符串都是有序的，如果有任何字符串没有被排序/排序，结果将被标记为关闭。

**示例:**

## 蟒蛇 3

```
# initializing list
test_list = ["dent", "flop", "most", "cent"]

# printing original list
print("The original list is : " + str(test_list))

res = True
for ele in test_list:

    # check for ordered string
    if ele != ''.join(sorted(ele)):
        res = False
        break

# printing result
print("Are all strings ordered ? : " + str(res))
```

**输出:**

> 原单是:['凹痕'，'翻牌'，'最多'，'分'
> 
> 所有字符串都是有序的吗？:真

**方法二:** *使用* [*全部()*](https://www.geeksforgeeks.org/any-all-in-python/) *和* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)

在这种情况下，避免了循环，并且使用 all()检查所有要排序的字符串，如果所有元素在特定条件下都返回 true，则返回 True。

**示例:**

## 蟒蛇 3

```
# initializing list
test_list = ["dent", "flop", "most", "cent"]

# printing original list
print("The original list is : " + str(test_list))

# using all() to check all elements to be sorted
res = all(ele == ''.join(sorted(ele)) for ele in test_list)

# printing result
print("Are all strings ordered ? : " + str(res))
```

**输出:**

> 原单是:['凹痕'，'翻牌'，'最多'，'分'
> 
> 所有字符串都是有序的吗？:真
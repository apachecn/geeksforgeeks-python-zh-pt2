# Python 程序查找好恶数

> 原文:[https://www . geesforgeks . org/python-program-to-find-好恶数/](https://www.geeksforgeeks.org/python-program-to-find-number-of-likes-and-dislikes/)

爱丽丝和鲍勃列了一个话题清单，两个人都投票决定他们喜欢还是不喜欢这个话题。他们写 0 表示不喜欢，写 1 表示喜欢。任务是统计他们都喜欢或不喜欢的话题数量。

**示例:**

> **输入:**爱丽丝=“010101”鲍勃=“101101”
> **输出:** 3
> 爱丽丝和鲍勃都喜欢第 4 和第 6 个话题，不喜欢第 5 个话题。因此，输出为 3。
> 
> **输入:**Alice =“111111”bob =“000000”
> **输出:**0
> Alice 和 bob 之间没有共同的好恶。因此，输出为 0。
> 
> **输入:**爱丽丝=“110000”鲍勃=“110011”
> **输出:** 4
> 爱丽丝和鲍勃都喜欢第 1 和第 2 个话题，不喜欢第 3 和第 4 个话题。因此，结果是 4。

**进场:**

*   首先，我们必须遍历由 alice 的好恶组成的字符串的每个字符。
*   然后，我们必须将其与包含鲍勃好恶的字符串的相应条目进行比较。
*   最后，我们将统计相似条目的数量并打印。

下面是实现。

```
# function to obtain no 
# of topics both alice and 
# bob like 
def commontopics(alice, bob):

    # initiate count with 0
    count = 0

    # iterating through alice
    for i in range(0,len(alice)):

        # comparing with corresponding
        # bob entry
        if alice[i] == bob[i]:

            # counting similar entries
            count += 1 

    # printing the count         
    print(count) 

#main function 
def main():

    commontopics("010101", "101101")
    commontopics("111111", "000000")
    commontopics("110000", "110011")

# driver code
if __name__ == "__main__":
    main()

# This code is contributed by SrujayReddy
```

**输出:**

```
3
0
4

```
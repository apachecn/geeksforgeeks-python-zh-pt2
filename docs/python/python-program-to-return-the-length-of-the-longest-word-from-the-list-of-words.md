# 从单词列表中返回最长单词长度的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-return-从单词列表中最长单词的长度/](https://www.geeksforgeeks.org/python-program-to-return-the-length-of-the-longest-word-from-the-list-of-words/)

问题是要遍历数组中的所有单词，程序应该返回最长的单词。例如，我们有一个数组，我们有字母形式的数字，现在当我们传递这个数组作为输入时，我们应该得到最长的那个单词。下面我用一个例子来解释它，以便给出一个详细的观点。
**例:**

> **输入:**【【一】【二】【三】【四】】
> **输出:**三
> **解释:**
> 当我们将上述数组作为输入传递时，我们的程序将检查哪个单词或哪个值具有最大长度，在完全迭代数组后，它将返回最长长度的单词。

**方法 1#:** 迭代寻找更长的单词。

**进场:**

1.  首先声明一个名为“最长长度”的函数，该函数接受一个列表作为参数。
2.  现在，列一个清单，列出所有的值。
3.  我们将采用这个列表，并使用 for 循环遍历每个项目。
4.  然后我们取两个变量 max1 和 temp 来存储最大长度和最长长度的单词。
5.  完成上述步骤后，我们取列表中的第一个值和第一个值的长度进行比较。
6.  完成上述步骤后，我们使用 for 循环比较列表中的项目。下面我已经提到了逻辑。
7.  完成上述步骤后，运行程序，然后我们将获得所需的结果。

**实施:**

## 蟒蛇 3

```
# function to find the longest
# length in the list
def longestLength(a):
    max1 = len(a[0])
    temp = a[0]

    # for loop to traverse the list
    for i in a:
        if(len(i) > max1):

            max1 = len(i)
            temp = i

    print("The word with the longest length is:", temp,
          " and length is ", max1)

# Driver Program
a = ["one", "two", "third", "four"]
longestLength(a)
```

**输出:**

```
The word with the longest length is: third  and length is  5
```

**方法 2#:** 使用排序()。

**进场:**

1.  首先声明一个名为“最长长度”的函数，该函数接受一个列表作为参数。
2.  现在，列一个清单，列出所有的值。
3.  我们将采用这个列表，并使用 for 循环遍历每个项目。
4.  然后我们取一个名为最终列表的空列表，并将附加所有项目。
5.  追加后，我们将使用 sort()方法对列表进行排序。
6.  现在，当列表被排序时，我们可以得到最长的长度，并且可以显示它。
7.  完成上述步骤后，运行程序，然后我们将获得所需的结果。

## 蟒蛇 3

```
# function to find the longest length in the list
def longestLength(words):
    finalList = []

    for word in words:
        finalList.append((len(word), word))

    finalList.sort()

    print("The word with the longest length is:", finalList[-1][1],
          " and length is ", len(finalList[-1][1]))

# Driver Program
a = ["one", "two", "third", "four"]
longestLength(a)
```

**输出:**

```
The word with the longest length is: third  and length is  5
```
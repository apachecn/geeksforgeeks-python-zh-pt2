# Python |程序实现简单的 FLAMES 游戏

> 原文:[https://www . geesforgeks . org/python-程序到实现-简单-火焰-游戏/](https://www.geeksforgeeks.org/python-program-to-implement-simple-flames-game/)

Python 是一种多用途语言，人们可以用它做任何事情。Python 也可以用于游戏开发。让我们创建一个简单的火焰游戏，而不使用任何外部游戏库，如 PyGame。
**FLAMES** 是一款以首字母缩略词命名的热门游戏:朋友、恋人、深情、婚姻、敌人、兄弟姐妹。这个游戏不能准确预测一个人是否适合你，但是和你的朋友一起玩这个游戏会很有趣。

这个游戏有两个步骤:

*   取这两个名字。
*   删除常见字符及其各自的常见事件。
*   获取剩余字符的计数。
*   将火焰字母作为[“F”、“L”、“A”、“M”、“E”、“S”]
*   用我们得到的计数开始移除字母。
*   最后一个过程就是结果的字母。

**示例:**

```py
Input :   player1 name : AJAY
          player 2 name : PRIYA

Output : Relationship status : Friends
```

**解释:**在上面给定的两个名字中，A 和 Y 是在两个名字中出现一次的共同字母(共同计数)，所以我们从两个名字中删除这些字母。现在数一下剩下的字母总数，是 5 个。现在开始用我们得到的计数一个接一个地从火焰中移除字母，持续这个过程的字母就是结果。

计数以逆时针循环方式进行。

> 火焰
> 计数从 F 开始， E 在第 5 次计数，所以我们移除 E 并再次开始计数，但是 A 这次从 S 开始
> FLAMS
> M 在第 5 次计数，所以我们移除 M 并从 S 开始计数
> FLAS
> S 在第 5 次计数，所以我们从 f 移除 S 并开始计数
> FLA
> L 在第 5 次计数，所以我们移除 L 并从 A 开始计数
> FA
> A 在第 5 次计数，所以我们移除 A。现在我们只剩下一个字母，所以这是最终答案。
> F
> 所以，关系是 F 即朋友。

**方法:**以两个名字作为输入，然后移除共同的字符及其各自的共同出现。出于删除的目的，我们创建了用户定义的 remove_match_char 函数，它有两个参数，分别为 list1 和 list2，分别存储两个玩家名字的字符列表，并返回串联列表的列表(list1 + "*" flagst2)和存储在 ret_list 变量中的标志值。删除所有常见字符后，计算剩余字符的总数，然后创建一个带有 FLAMES 首字母缩写词的结果列表，即[“朋友”、“爱情”、“感情”、“婚姻”、“敌人”、“兄弟姐妹”]。现在开始一个一个地删除单词，直到列表不仅仅包含一个单词，使用我们得到的总数。留在最后的字，就是结果。

下面是实现:

## 蟒蛇 3

```py
# function for removing common characters
# with their respective occurrences
def remove_match_char(list1, list2):

    for i in range(len(list1)) :
        for j in range(len(list2)) :

            # if common character is found
            # then remove that character
            # and return list of concatenated
            # list with True Flag
            if list1[i] == list2[j] :
                c = list1[i]

                # remove character from the list
                list1.remove(c)
                list2.remove(c)

                # concatenation of two list elements with *
                # * is act as border mark here
                list3 = list1 + ["*"] + list2

                # return the concatenated list with True flag
                return [list3, True]

    # no common characters is found
    # return the concatenated list with False flag
    list3 = list1 + ["*"] + list2
    return [list3, False]

# Driver code
if __name__ == "__main__" :

    # take first name  
    p1 = input("Player 1 name : ")

    # converted all letters into lower case
    p1 = p1.lower()

    # replace any space with empty string
    p1.replace(" ", "")

    # make a list of letters or characters
    p1_list = list(p1)

    # take 2nd name
    p2 = input("Player 2 name : ")
    p2 = p2.lower()
    p2.replace(" ", "")
    p2_list = list(p2)

    # taking a flag as True initially
    proceed = True

    # keep calling remove_match_char function
    # until common characters is found or
    # keep looping until proceed flag is True
    while proceed :

        # function calling and store return value
        ret_list = remove_match_char(p1_list, p2_list)

        # take out concatenated list from return list
        con_list = ret_list[0]

        # take out flag value from return list
        proceed = ret_list[1]

        # find the index of "*" / border mark
        star_index = con_list.index("*")

        # list slicing perform

        # all characters before * store in p1_list
        p1_list = con_list[ : star_index]

        # all characters after * store in p2_list
        p2_list = con_list[star_index + 1 : ]

    # count total remaining characters
    count = len(p1_list) + len(p2_list)

    # list of FLAMES acronym
    result = ["Friends", "Love", "Affection", "Marriage", "Enemy", "Siblings"]

    # keep looping until only one item
    # is not remaining in the result list
    while len(result) > 1 :

        # store that index value from
        # where we have to perform slicing.
        split_index = (count % len(result) - 1)

        # this steps is done for performing
        # anticlock-wise circular fashion counting.
        if split_index >= 0 :

            # list slicing
            right = result[split_index + 1 : ]
            left = result[ : split_index]

            # list concatenation
            result = right + left

        else :
            result = result[ : len(result) - 1]

    # print final result
    print("Relationship status :", result[0])
```

**输出:**

```py
Player 1 name : ANKIT
Player 2 name : DEEPIKA
Relationship status : Marriage
```
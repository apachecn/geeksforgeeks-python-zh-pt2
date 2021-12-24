# 用于猜字游戏的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序换单词猜谜游戏/](https://www.geeksforgeeks.org/python-program-for-word-guessing-game/)

Python 是一种强大的多用途编程语言，被多个巨头公司使用。它有简单易用的语法，使它成为第一次尝试学习计算机编程的人的完美语言。它是一种高级编程语言，其核心设计理念是代码可读性和语法，允许程序员用几行代码表达概念。
在本文中，我们将使用随机模块制作一个猜字游戏。这个游戏是为学习 python 代码的初学者准备的，并向他们简要介绍如何使用字符串、循环和条件(If，else)语句。

> **随机模块** :
> 有时候我们希望电脑在给定的范围内挑选一个随机数，从列表中挑选一个随机元素，从一副牌中挑选一张随机牌，掷硬币等。随机模块提供对支持这些类型操作的函数的访问。一个这样的操作是 random.choice()方法(从列表、元组或字符串中返回随机项。)来从我们创建的单词列表中选择一个随机单词。

在这个游戏中，有一个单词列表，我们的翻译将从其中选择 1 个随机单词。用户首先必须输入他们的名字，然后，将被要求猜任何字母表。如果随机单词包含该字母表，它将显示为输出(位置正确)，否则程序将要求您猜测另一个字母表。用户将被给予 12 次机会(可以相应地改变)来猜测完整的单词。
下面是 Python 实现:

## 蟒蛇 3

```
import random
# library that we use in order to choose
# on random words from a list of words

name = input("What is your name? ")
# Here the user is asked to enter the name first

print("Good Luck ! ", name)

words = ['rainbow', 'computer', 'science', 'programming',
         'python', 'mathematics', 'player', 'condition',
         'reverse', 'water', 'board', 'geeks']

# Function will choose one random
# word from this list of words
word = random.choice(words)

print("Guess the characters")

guesses = ''

# any number of turns can be used here
turns = 12

while turns > 0:

    # counts the number of times a user fails
    failed = 0

    # all characters from the input
    # word taking one at a time.
    for char in word:

        # comparing that character with
        # the character in guesses
        if char in guesses:
            print(char)

        else:
            print("_")

            # for every failure 1 will be
            # incremented in failure
            failed += 1

    if failed == 0:
        # user will win the game if failure is 0
        # and 'You Win' will be given as output
        print("You Win")

        # this print the correct word
        print("The word is: ", word)
        break

    # if user has input the wrong alphabet then
    # it will ask user to enter another alphabet
    guess = input("guess a character:")

    # every input character will be stored in guesses
    guesses += guess

    # check input with the character in word
    if guess not in word:

        turns -= 1

        # if the character doesn’t match the word
        # then “Wrong” will be given as output
        print("Wrong")

        # this will print the number of
        # turns left for the user
        print("You have", + turns, 'more guesses')

        if turns == 0:
            print("You Loose")
```

**输出:**

```
What is your name? Gautam
Good Luck!  Gautam
Guess the characters
_
_
_
_
_
guess a character:g
g
_
_
_
_
guess a character:e
g
e
e
_
_
guess a character:k
g
e
e
k
_
guess a character:s
g
e
e
k
s
You Win
The word is:  geeks 

```
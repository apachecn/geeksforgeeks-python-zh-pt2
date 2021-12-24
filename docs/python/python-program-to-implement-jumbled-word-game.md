# Python |实现冗杂文字游戏的程序

> 原文:[https://www . geesforgeks . org/python-程序到实现-冗杂-文字游戏/](https://www.geeksforgeeks.org/python-program-to-implement-jumbled-word-game/)

Python 是一种多用途语言，人们可以用它做任何事情。Python 也可以用于游戏开发。让我们创建一个简单的冗杂的文字游戏，而不使用任何外部游戏库，如 PyGame。

**冗杂单词游戏:**冗杂的单词给玩家，玩家要重新排列单词的字符才能做出正确有意义的单词。

**示例:**

```
Input: erwta
Output: water

Input: mehtatasmci
Output: mathematics

Input: keseg
Output: geeks
```

这是一个两人游戏，首先程序使用随机模块的 choice()方法从给定的单词列表中选择一个随机单词。使用随机模块的抽样方法对所选单词的字符进行混排后，将混排的单词显示在屏幕上。当前玩家应该给出答案；如果它在重新排列字符后给出了正确的答案，那么玩家的分数就会增加 1，否则就不会。退出游戏后，根据分数决定获胜者。

**使用内置功能:**

```
choice() method randomly choose any word from the list.
sample() method shuffling the characters of the word.
```

**用户自定义功能:**

> **选择():**从列表中选择随机单词。
> **混动():**移动所选单词的字符。我们必须传递一个选定的词作为论据。
> **感谢():**显示双方选手的最终得分。传递玩家 1 的名字、玩家 2 的名字和玩家 1、玩家 2 的分数作为参数。
> **check_win() :** 宣布获胜者。传递玩家 1 的名称、玩家 2 的名称以及玩家 1 和玩家 2 的分数作为参数。
> **play() :** 开始游戏。

下面是实现:

## 蟒蛇 3

```
# Python program for jumbled words game.

# import random module
import random

# function for choosing random word.
def choose():
    # list of word
    words = ['rainbow', 'computer', 'science', 'programming',
             'mathematics', 'player', 'condition', 'reverse',
             'water', 'board', 'geeks']

    # choice() method randomly choose
    # any word from the list.
    pick = random.choice(words)

    return pick

# Function for shuffling the
# characters of the chosen word.
def jumble(word):
    # sample() method shuffling the characters of the word
    random_word = random.sample(word, len(word))

    # join() method join the elements
    # of the iterator(e.g. list) with particular character .
    jumbled = ''.join(random_word)
    return jumbled

# Function for showing final score.
def thank(p1n, p2n, p1, p2):
    print(p1n, 'Your score is :', p1)
    print(p2n, 'Your score is :', p2)

    # check_win() function calling
    check_win(p1n, p2n, p1, p2)

    print('Thanks for playing...')

# Function for declaring winner
def check_win(player1, player2, p1score, p2score):
    if p1score > p2score:
        print("winner is :", player1)
    elif p2score > p1score:
        print("winner is :", player2)
    else:
        print("Draw..Well Played guys..")

# Function for playing the game.
def play():
    # enter player1 and player2 name
    p1name = input("player 1, Please enter your name :")
    p2name = input("Player 2 , Please enter your name: ")

    # variable for counting score.
    pp1 = 0
    pp2 = 0

    # variable for counting turn
    turn = 0

    # keep looping
    while True:

        # choose() function calling
        picked_word = choose()

        # jumble() function calling
        qn = jumble(picked_word)
        print("jumbled word is :", qn)

        # checking turn is odd or even
        if turn % 2 == 0:

            # if turn no. is even
            # player1 turn
            print(p1name, 'Your Turn.')

            ans = input("what is in your mind? ")

            # checking ans is equal to picked_word or not
            if ans == picked_word:

                # incremented by 1
                pp1 += 1

                print('Your score is :', pp1)
                turn += 1

            else:
                print("Better luck next time ..")

                # player 2 turn
                print(p2name, 'Your turn.')

                ans = input('what is in your mind? ')

                if ans == picked_word:
                    pp2 += 1
                    print("Your Score is :", pp2)

                else:
                    print("Better luck next time...correct word is :", picked_word)

                c = int(input("press 1 to continue and 0 to quit :"))

                # checking the c is equal to 0 or not
                # if c is equal to 0 then break out
                # of the while loop o/w keep looping.
                if c == 0:
                    # thank() function calling
                    thank(p1name, p2name, pp1, pp2)
                    break

        else:

            # if turn no. is odd
            # player2 turn
            print(p2name, 'Your turn.')
            ans = input('what is in your mind? ')

            if ans == picked_word:
                pp2 += 1
                print("Your Score is :", pp2)
                turn += 1

            else:
                print("Better luck next time.. :")
                print(p1name, 'Your turn.')
                ans = input('what is in your mind? ')

                if ans == picked_word:
                    pp1 += 1
                    print("Your Score is :", pp1)

                else:
                    print("Better luck next time...correct word is :", picked_word)

                    c = int(input("press 1 to continue and 0 to quit :"))

                    if c == 0:
                        # thank() function calling
                        thank(p1name, p2name, pp1, pp2)
                        break

            c = int(input("press 1 to continue and 0 to quit :"))
            if c == 0:
                # thank() function calling
                thank(p1name, p2name, pp1, pp2)
                break

# Driver code
if __name__ == '__main__':

    # play() function calling
    play()
```

**输出:**

```
player 1, Please enter your name :Ankit
Player 2 , Please enter your name: John
jumbled word is : abiwrno
Ankit Your Turn.
what is in your mind? rainbow
Your score is : 1
jumbled word is : rbado
John Your turn.
what is in your mind? borad
Better luck next time.. :
Ankit Your turn.
what is in your mind? board
Your Score is : 2
press 1 to continue and 0 to quit :1
jumbled word is : wbrinao
John Your turn.
what is in your mind? rainbow
Your Score is : 1

*press 1 to continue and 0 to quit :1*

jumbled word is : bnrawio
Ankit Your Turn.
what is in your mind? rainbow
Your score is : 3
jumbled word is : enecsic
John Your turn.
what is in your mind? science
Your Score is : 2
press 1 to continue and 0 to quit :0
Ankit Your score is : 3
John Your score is : 2
winner is : Ankit
Thanks for playing...
```
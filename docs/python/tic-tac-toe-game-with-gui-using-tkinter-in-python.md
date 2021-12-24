# 使用 Python 中 tkinter 的 GUI 的井字游戏

> 原文:[https://www . geesforgeks . org/TIC-tac-toe-game-with-GUI-use-tkinter-in-python/](https://www.geeksforgeeks.org/tic-tac-toe-game-with-gui-using-tkinter-in-python/)

井字游戏(美式英语)、零号和十字(英式英语)或 Xs 和 Os 是一个纸笔游戏，由 X 和 O 两个玩家轮流在 3×3 的格子中标记空格。成功地在水平、垂直或对角线行中放置三个标记的玩家是赢家。

tkinter Python 库用于创建 GUI。有两个选项可以玩游戏，与系统一起**或与另一个玩家一起**。

一个小的获胜策略被用来玩系统。该系统将试图找到最好的地方把它的零或交叉，系统将赢得或试图阻止玩家获胜。

### 方法:

*   创建包含选择按钮的登陆页面:单人或多人。
*   创建一个包含九块牌的游戏板，与其他细节一起玩游戏(例如，与系统或其他玩家一起玩，轮到谁等)。).
*   允许玩家按下磁贴并检查游戏状态(即铁游戏，任何玩家赢得比赛或游戏仍在运行)。
*   显示消息，谁赢了比赛。

#### 其他功能的描述:

*   gameboard_pc()和 gameboard_pl()将创建另一个几何图形来玩游戏。它将在 3×3 的游戏棋盘上增加 9 个按钮(三排按钮，每排包含三个按钮)。
*   get_text_pc()和 get_text()函数会在按下按钮时将文本放在按钮上。
*   pc()函数将决定系统的下一步。
*   winner()函数将检查玩家是否赢得了比赛。
*   isfree()函数将检查玩家是否可以放入硬币。
*   isfull()函数将检查电路板是否已满。

**下面是上面游戏的代码:**

## 蟒蛇 3

```
# Tic Tac Toe game with GUI
# using tkinter

# importing all necessary libraries
import random
import tkinter
from tkinter import *
from functools import partial
from tkinter import messagebox
from copy import deepcopy

# sign variable to decide the turn of which player
sign = 0

# Creates an empty board
global board
board = [[" " for x in range(3)] for y in range(3)]

# Check l(O/X) won the match or not
# according to the rules of the game
def winner(b, l):
    return ((b[0][0] == l and b[0][1] == l and b[0][2] == l) or
            (b[1][0] == l and b[1][1] == l and b[1][2] == l) or
            (b[2][0] == l and b[2][1] == l and b[2][2] == l) or
            (b[0][0] == l and b[1][0] == l and b[2][0] == l) or
            (b[0][1] == l and b[1][1] == l and b[2][1] == l) or
            (b[0][2] == l and b[1][2] == l and b[2][2] == l) or
            (b[0][0] == l and b[1][1] == l and b[2][2] == l) or
            (b[0][2] == l and b[1][1] == l and b[2][0] == l))

# Configure text on button while playing with another player
def get_text(i, j, gb, l1, l2):
    global sign
    if board[i][j] == ' ':
        if sign % 2 == 0:
            l1.config(state=DISABLED)
            l2.config(state=ACTIVE)
            board[i][j] = "X"
        else:
            l2.config(state=DISABLED)
            l1.config(state=ACTIVE)
            board[i][j] = "O"
        sign += 1
        button[i][j].config(text=board[i][j])
    if winner(board, "X"):
        gb.destroy()
        box = messagebox.showinfo("Winner", "Player 1 won the match")
    elif winner(board, "O"):
        gb.destroy()
        box = messagebox.showinfo("Winner", "Player 2 won the match")
    elif(isfull()):
        gb.destroy()
        box = messagebox.showinfo("Tie Game", "Tie Game")

# Check if the player can push the button or not
def isfree(i, j):
    return board[i][j] == " "

# Check the board is full or not
def isfull():
    flag = True
    for i in board:
        if(i.count(' ') > 0):
            flag = False
    return flag

# Create the GUI of game board for play along with another player
def gameboard_pl(game_board, l1, l2):
    global button
    button = []
    for i in range(3):
        m = 3+i
        button.append(i)
        button[i] = []
        for j in range(3):
            n = j
            button[i].append(j)
            get_t = partial(get_text, i, j, game_board, l1, l2)
            button[i][j] = Button(
                game_board, bd=5, command=get_t, height=4, width=8)
            button[i][j].grid(row=m, column=n)
    game_board.mainloop()

# Decide the next move of system
def pc():
    possiblemove = []
    for i in range(len(board)):
        for j in range(len(board[i])):
            if board[i][j] == ' ':
                possiblemove.append([i, j])
    move = []
    if possiblemove == []:
        return
    else:
        for let in ['O', 'X']:
            for i in possiblemove:
                boardcopy = deepcopy(board)
                boardcopy[i[0]][i[1]] = let
                if winner(boardcopy, let):
                    return i
        corner = []
        for i in possiblemove:
            if i in [[0, 0], [0, 2], [2, 0], [2, 2]]:
                corner.append(i)
        if len(corner) > 0:
            move = random.randint(0, len(corner)-1)
            return corner[move]
        edge = []
        for i in possiblemove:
            if i in [[0, 1], [1, 0], [1, 2], [2, 1]]:
                edge.append(i)
        if len(edge) > 0:
            move = random.randint(0, len(edge)-1)
            return edge[move]

# Configure text on button while playing with system
def get_text_pc(i, j, gb, l1, l2):
    global sign
    if board[i][j] == ' ':
        if sign % 2 == 0:
            l1.config(state=DISABLED)
            l2.config(state=ACTIVE)
            board[i][j] = "X"
        else:
            button[i][j].config(state=ACTIVE)
            l2.config(state=DISABLED)
            l1.config(state=ACTIVE)
            board[i][j] = "O"
        sign += 1
        button[i][j].config(text=board[i][j])
    x = True
    if winner(board, "X"):
        gb.destroy()
        x = False
        box = messagebox.showinfo("Winner", "Player won the match")
    elif winner(board, "O"):
        gb.destroy()
        x = False
        box = messagebox.showinfo("Winner", "Computer won the match")
    elif(isfull()):
        gb.destroy()
        x = False
        box = messagebox.showinfo("Tie Game", "Tie Game")
    if(x):
        if sign % 2 != 0:
            move = pc()
            button[move[0]][move[1]].config(state=DISABLED)
            get_text_pc(move[0], move[1], gb, l1, l2)

# Create the GUI of game board for play along with system
def gameboard_pc(game_board, l1, l2):
    global button
    button = []
    for i in range(3):
        m = 3+i
        button.append(i)
        button[i] = []
        for j in range(3):
            n = j
            button[i].append(j)
            get_t = partial(get_text_pc, i, j, game_board, l1, l2)
            button[i][j] = Button(
                game_board, bd=5, command=get_t, height=4, width=8)
            button[i][j].grid(row=m, column=n)
    game_board.mainloop()

# Initialize the game board to play with system
def withpc(game_board):
    game_board.destroy()
    game_board = Tk()
    game_board.title("Tic Tac Toe")
    l1 = Button(game_board, text="Player : X", width=10)
    l1.grid(row=1, column=1)
    l2 = Button(game_board, text = "Computer : O",
                width = 10, state = DISABLED)

    l2.grid(row = 2, column = 1)
    gameboard_pc(game_board, l1, l2)

# Initialize the game board to play with another player
def withplayer(game_board):
    game_board.destroy()
    game_board = Tk()
    game_board.title("Tic Tac Toe")
    l1 = Button(game_board, text = "Player 1 : X", width = 10)

    l1.grid(row = 1, column = 1)
    l2 = Button(game_board, text = "Player 2 : O", 
                width = 10, state = DISABLED)

    l2.grid(row = 2, column = 1)
    gameboard_pl(game_board, l1, l2)

# main function
def play():
    menu = Tk()
    menu.geometry("250x250")
    menu.title("Tic Tac Toe")
    wpc = partial(withpc, menu)
    wpl = partial(withplayer, menu)

    head = Button(menu, text = "---Welcome to tic-tac-toe---",
                  activeforeground = 'red',
                  activebackground = "yellow", bg = "red", 
                  fg = "yellow", width = 500, font = 'summer', bd = 5)

    B1 = Button(menu, text = "Single Player", command = wpc, 
                activeforeground = 'red',
                activebackground = "yellow", bg = "red", 
                fg = "yellow", width = 500, font = 'summer', bd = 5)

    B2 = Button(menu, text = "Multi Player", command = wpl, activeforeground = 'red',
                activebackground = "yellow", bg = "red", fg = "yellow",
                width = 500, font = 'summer', bd = 5)

    B3 = Button(menu, text = "Exit", command = menu.quit, activeforeground = 'red',
                activebackground = "yellow", bg = "red", fg = "yellow",
                width = 500, font = 'summer', bd = 5)
    head.pack(side = 'top')
    B1.pack(side = 'top')
    B2.pack(side = 'top')
    B3.pack(side = 'top')
    menu.mainloop()

# Call main function
if __name__ == '__main__':
    play()
```

**输出:**

<video class="wp-video-shortcode" id="video-536189-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210104215436/send.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210104215436/send.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210104215436/send.mp4)</video>
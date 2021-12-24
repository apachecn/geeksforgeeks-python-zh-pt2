# 使用 Python 中的 Turtle 创建一个简单的双人游戏

> 原文:[https://www . geesforgeks . org/create-a-simple-two-player-game-use-turtle-in-python/](https://www.geeksforgeeks.org/create-a-simple-two-player-game-using-turtle-in-python/)

**先决条件:**[Python 中的海龟编程](https://www.geeksforgeeks.org/turtle-programming-python/)

**TurtleMove** 游戏基本上是一款运气为主的游戏。在这个游戏中两个玩家(红色&蓝色)，用自己的乌龟(物体)玩游戏。

### **如何玩**

游戏在具有一些边界的预定义网格中进行。

*   两位玩家将乌龟移动一个单位距离。
*   现在两个玩家都掷硬币:
*   如果是 HEAD，那么向右转
*   否则左转
*   3)现在重复 1 和 2，直到两只乌龟都躺在边界上

### 海龟 Python 中的实现

*   首先，为网格边界创建一个龟屏对象。
*   现在创建了两个海龟(红色和蓝色)，每个玩家一个。
*   使用**海龟向前(50)** 方法将两只海龟移动一个单位距离。
*   使用 [**随机范围(0，2)**](https://www.geeksforgeeks.org/randrange-in-python/) 决定转弯，即 0 代表左侧，1 代表右侧。
*   每次移动后，每只海龟的位置都会被检查，如果有海龟越过边界，那么这只海龟就输了。

下面是实现

## 蟒蛇 3

```
import random
import turtle

# function to check whether turtle
# is in Screen or not
def isInScreen(win, turt):

    # getting the end points of turtle screen
    leftBound = -win.window_width() / 2
    rightBound = win.window_width() / 2
    topBound = win.window_height() / 2
    bottomBound = -win.window_height() / 2

    # getting the current position of the turtle
    turtleX = turt.xcor()
    turtleY = turt.ycor()

    # variable to store whether in screen or not
    stillIn = True

    # condition to check whether in screen or not
    if turtleX > rightBound or turtleX < leftBound:
        stillIn = False
    if turtleY > topBound or turtleY < bottomBound:
        stillIn = False

    # returning the result
    return stillIn

# function to check whether both turtle have
# different position or not
def sameposition(Red, Blue):
    if Red.pos() == Blue.pos():
        return False
    else:
        return True

#   main function
def main():

    # screen initialization for turtle
    wn = turtle.Screen()

    # Turtle Red initialization
    # instantiate a new turtle object
    # called 'Red'
    Red = turtle.Turtle()

    # set pencolor as red
    Red.pencolor("red")

    # set pensize as 5
    Red.pensize(5)

    # set turtleshape as turtle
    Red.shape('turtle')
    pos = Red.pos()

    # Turtle Blue initialization
    # instantiate a new turtle object
    # called 'Blue'
    Blue = turtle.Turtle()

    # set pencolor as blue
    Blue.pencolor("blue")

    # set pensize as 5
    Blue.pensize(5)

    # set turtleshape as turtle
    Blue.shape('turtle')

    # make the turtle invisible
    Blue.hideturtle()

    # don't draw when turtle moves
    Blue.penup()

    # move the turtle to a location 50
    # units away from Red
    Blue.goto(pos[0]+50, pos[1])

    # make the turtle visible
    Blue.showturtle()

    # draw when the turtle moves
    Blue.pendown()

    # variable to store whether turtles
    # are in screen or not
    mT = True
    jT = True

    # loop for the game
    while mT and jT and sameposition(Red, Blue):

        # coin flip for Red
        coinRed = random.randrange(0, 2)

        # angle for Red
        # random.randrange(0, 180)
        angleRed = 90

        # condition for left or right
        # based on coin
        if coinRed == 0:
            Red.left(angleRed)
        else:
            Red.right(angleRed)

        # coin flip for Blue
        coinBlue = random.randrange(0, 2)

        # angle for Blue
        # random.randrange(0, 180)
        angleBlue = 90

        # condition for left or right based
        # on coin
        if coinBlue == 0:
            Blue.left(angleBlue)
        else:
            Blue.right(angleBlue)

        # draw for Red
        Red.forward(50)

        # draw for Blue
        Blue.forward(50)

        # checking whether turtles are in the
        # screen or not
        mT = isInScreen(wn, Blue)
        jT = isInScreen(wn, Red)

    # set pencolor for Blue and Red as black
    Red.pencolor("black")
    Blue.pencolor("black")

    # condition check for draw or win
    if jT == True and mT == False:
        # writing results
        Red.write("Red Won", True, align="center",
                  font=("arial", 15, "bold"))

    elif mT == True and jT == False:

        # writing results
        Blue.write("Blue Won", True, align="center",
                   font=("arial", 15, "bold"))
    else:
        # writing results
        Red.write("Draw", True, align="center",
                  font=("arial", 15, "bold"))
        Blue.write("Draw", True, align="center",
                   font=("arial", 15, "bold"))

    # exit on close
    wn.exitonclick()

# Calling main function
main()
```

**输出:**

<video class="wp-video-shortcode" id="video-467234-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200807171432/game.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200807171432/game.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200807171432/game.mp4)</video>
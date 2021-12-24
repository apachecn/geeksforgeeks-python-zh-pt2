# 使用 Python 中的 Turtle 绘制移动对象

> 原文:[https://www . geeksforgeeks . org/draw-move-object-use-turtle-in-python/](https://www.geeksforgeeks.org/draw-moving-object-using-turtle-in-python/)

#### 先决条件: [<u>蟒蛇龟基础知识</u>](https://www.geeksforgeeks.org/turtle-programming-python/)

**Turtle** 是 python 中的一个内置模块。它提供使用屏幕(纸板)和乌龟(钢笔)的绘图。要在屏幕上画东西，我们需要移动乌龟。要移动海龟，有一些功能，例如向前()，向后()，等等。

#### 1.)移动对象(球) :

> 使用以下步骤:
> 
> *   Import turtle package.
> *   Set the screen size and color.
> *   Make turtle-shaped objects with colors.
> *   Form an object (ball-composed of colored circles).
> *   Call the function of making objects repeatedly to clear the screen.

下面是实现:

<gfg-tab role="tab" slot="tab" id="gfg-tab-0">Python3</gfg-tab> <gfg-panel role="tabpanel" slot="panel" id="gfg-panel-0" data-code-lang="python3">```py
# import turtle package
import turtle

# function for movement of an object 
def moving_object(move):

    # to fill the color in ball
    move.fillcolor('orange') 

    # start color filling
    move.begin_fill() 

    # draw circle
    move.circle(20)  

    # end color filling
    move.end_fill()             

# Driver Code
if __name__ == "__main__" :

    # create a screen object
    screen = turtle.Screen() 

    # set screen size
    screen.setup(600,600)    

    # screen background color
    screen.bgcolor('green')   

    # screen updaion 
    screen.tracer(0)           

    # create a turtle object object
    move = turtle.Turtle() 

    # set a turtle object color
    move.color('orange')

    # set turtle object speed
    move.speed(0) 

    # set turtle object width
    move.width(2)     

    # hide turtle object
    move.hideturtle()          

    # turtle object in air
    move.penup()               

    # set initial position
    move.goto(-250, 0) 

    # move turtle object to surface
    move.pendown()             

    # infinite loop
    while True :

        # clear turtle work
        move.clear()  

        # call function to draw ball
        moving_object(move)   

        # update screen
        screen.update()    

        # forward motion by turtle object
        move.forward(0.5) 
```</gfg-panel>
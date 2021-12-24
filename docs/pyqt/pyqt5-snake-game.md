# pyqt 5–蛇游戏

> 原文:[https://www.geeksforgeeks.org/pyqt5-snake-game/](https://www.geeksforgeeks.org/pyqt5-snake-game/)

在本文中，我们将看到如何使用 PyQt5 设计简单的蛇游戏。

**Snake** 是一个视频游戏概念的通称，玩家操纵一条越来越长的线，线本身是主要障碍。这个概念起源于 1976 年的街机游戏《封锁》，实现 snake 的简易性为许多平台带来了数百个版本(其中一些版本的标题中有 Snake 或 worm 两个字)。

> **实施步骤:**
> 1。创建一个主窗口添加状态栏到其中，显示分数并创建一个棋盘类的对象并将其添加为中心小部件
> 2。创建一个名为 board 的类，它继承了 QFrame
> 3。在板类内部创建一个定时器对象，在一定时间后调用定时器方法
> 4。计时器内的方法调用蛇游戏的其他动作如运动、吃的食物和如果蛇自杀
> 5。创建一个按键事件方法，检查箭头键是否被按下，并根据它改变蛇的方向。
> 6。创建一个绘制蛇和食物的绘制事件方法
> 7。创建移动方法，按照
> 8 的方向移动蛇。创建食物吃的方法，检查蛇的当前位置和位置。如果食物被吃了，移除当前食物，增加蛇的长度，并在随机位置放置一个新的食物。
> 9。创建检查自杀方法，检查蛇头位置是否与身体位置相似，如果匹配，停止计时器并显示消息

下面是实现

```py
# importing libraries
from PyQt5.QtCore import * 
from PyQt5.QtWidgets import * 
from PyQt5.QtGui import * 
import random
import sys

# creating game window
class Window(QMainWindow):
    def __init__(self):
        super(Window, self).__init__()

        # creating a board object
        self.board = Board(self)

        # creating a status bar to show result
        self.statusbar = self.statusBar()

        # adding border to the status bar
        self.statusbar.setStyleSheet("border : 2px solid black;")

        # calling showMessage method when signal received by board
        self.board.msg2statusbar[str].connect(self.statusbar.showMessage)

        # adding board as a central widget
        self.setCentralWidget(self.board)

        # setting title to the window
        self.setWindowTitle('Snake game')

        # setting geometry to the window
        self.setGeometry(100, 100, 600, 400)

        # starting the board object
        self.board.start()

        # showing the main window
        self.show()

# creating a board class
# that inherits QFrame
class Board(QFrame):

    # creating signal object
    msg2statusbar = pyqtSignal(str)

    # speed of the snake
    # timer countdown time
    SPEED = 80

    # block width and height
    WIDTHINBLOCKS = 60
    HEIGHTINBLOCKS = 40

    # constructor
    def __init__(self, parent):
        super(Board, self).__init__(parent)

        # creating a timer
        self.timer = QBasicTimer()

        # snake
        self.snake = [[5, 10], [5, 11]]

        # current head x head
        self.current_x_head = self.snake[0][0]
        # current y head
        self.current_y_head = self.snake[0][1]

        # food list
        self.food = []

        # growing is false
        self.grow_snake = False

        # board list
        self.board = []

        # direction
        self.direction = 1

        # called drop food method
        self.drop_food()

        # setting focus
        self.setFocusPolicy(Qt.StrongFocus)

    # square width method
    def square_width(self):
        return self.contentsRect().width() / Board.WIDTHINBLOCKS

    # square height
    def square_height(self):
        return self.contentsRect().height() / Board.HEIGHTINBLOCKS

    # start method
    def start(self):
        # msg for status bar
        # score = current len - 2
        self.msg2statusbar.emit(str(len(self.snake) - 2))

        # starting timer
        self.timer.start(Board.SPEED, self)

    # paint event
    def paintEvent(self, event):

        # creating painter object
        painter = QPainter(self)

        # getting rectangle
        rect = self.contentsRect()

        # board top
        boardtop = rect.bottom() - Board.HEIGHTINBLOCKS * self.square_height()

        # drawing snake
        for pos in self.snake:
            self.draw_square(painter, rect.left() + pos[0] * self.square_width(),
                             boardtop + pos[1] * self.square_height())

        # drawing food
        for pos in self.food:
            self.draw_square(painter, rect.left() + pos[0] * self.square_width(),
                             boardtop + pos[1] * self.square_height())

    # drawing square
    def draw_square(self, painter, x, y):
        # color
        color = QColor(0x228B22)

        # painting rectangle
        painter.fillRect(x + 1, y + 1, self.square_width() - 2,
                         self.square_height() - 2, color)

    # key press event
    def keyPressEvent(self, event):

        # getting key pressed
        key = event.key()

        # if left key pressed
        if key == Qt.Key_Left:
            # if direction is not right
            if self.direction != 2:
                # set direction to left
                self.direction = 1

        # if right key is pressed
        elif key == Qt.Key_Right:
            # if direction is not left
            if self.direction != 1:
                # set direction to right
                self.direction = 2

        # if down key is pressed
        elif key == Qt.Key_Down:
            # if direction is not up
            if self.direction != 4:
                # set direction to down
                self.direction = 3

        # if up key is pressed
        elif key == Qt.Key_Up:
            # if direction is not down
            if self.direction != 3:
                # set direction to up
                self.direction = 4

    # method to move the snake
    def move_snake(self):

        # if direction is left change its position
        if self.direction == 1:
            self.current_x_head, self.current_y_head = self.current_x_head - 1, self.current_y_head

            # if it goes beyond left wall
            if self.current_x_head < 0:
                self.current_x_head = Board.WIDTHINBLOCKS - 1

        # if direction is right change its position
        if self.direction == 2:
            self.current_x_head, self.current_y_head = self.current_x_head + 1, self.current_y_head
            # if it goes beyond right wall
            if self.current_x_head == Board.WIDTHINBLOCKS:
                self.current_x_head = 0

        # if direction is down change its position
        if self.direction == 3:
            self.current_x_head, self.current_y_head = self.current_x_head, self.current_y_head + 1
            # if it goes beyond down wall
            if self.current_y_head == Board.HEIGHTINBLOCKS:
                self.current_y_head = 0

        # if direction is up change its position
        if self.direction == 4:
            self.current_x_head, self.current_y_head = self.current_x_head, self.current_y_head - 1
            # if it goes beyond up wall
            if self.current_y_head < 0:
                self.current_y_head = Board.HEIGHTINBLOCKS

        # changing head position
        head = [self.current_x_head, self.current_y_head]
        # inset head in snake list
        self.snake.insert(0, head)

        # if snake grow is False
        if not self.grow_snake:
            # pop the last element
            self.snake.pop()

        else:
            # show msg in status bar
            self.msg2statusbar.emit(str(len(self.snake)-2))
            # make grow_snake to false
            self.grow_snake = False

    # time event method
    def timerEvent(self, event):

        # checking timer id
        if event.timerId() == self.timer.timerId():

            # call move snake method
            self.move_snake()
            # call food collision method
            self.is_food_collision()
            # call is suicide method
            self.is_suicide()
            # update the window
            self.update()

    # method to check if snake collides itself
    def is_suicide(self):
        # traversing the snake
        for i in range(1, len(self.snake)):
            # if collision found
            if self.snake[i] == self.snake[0]:
                # show game ended msg in status bar
                self.msg2statusbar.emit(str("Game Ended"))
                # making background color black
                self.setStyleSheet("background-color : black;")
                # stopping the timer
                self.timer.stop()
                # updating the window
                self.update()

    # method to check if the food cis collied
    def is_food_collision(self):

        # traversing the position of the food
        for pos in self.food:
            # if food position is similar of snake position
            if pos == self.snake[0]:
                # remove the food
                self.food.remove(pos)
                # call drop food method
                self.drop_food()
                # grow the snake
                self.grow_snake = True

    # method to drop food on screen
    def drop_food(self):
        # creating random co-ordinates
        x = random.randint(3, 58)
        y = random.randint(3, 38)

        # traversing if snake position is not equal to the
        # food position so that food do not drop on snake
        for pos in self.snake:
            # if position matches
            if pos == [x, y]:
                # call drop food method again
                self.drop_food()

        # append food location
        self.food.append([x, y])

# main method
if __name__ == '__main__':
    app = QApplication([])
    window = Window()
    sys.exit(app.exec_())
```

**输出:**

<video class="wp-video-shortcode" id="video-422626-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200531025009/Snake-game-2020-05-31-02-49-23.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200531025009/Snake-game-2020-05-31-02-49-23.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200531025009/Snake-game-2020-05-31-02-49-23.mp4)</video>
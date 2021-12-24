# Python 中的蛇游戏–使用 Pygame 模块

> 原文:[https://www . geesforgeks . org/python 中的蛇游戏-使用-pygame-module/](https://www.geeksforgeeks.org/snake-game-in-python-using-pygame-module/)

蛇游戏是有史以来最受欢迎的街机游戏之一。在这个游戏中，玩家的主要目标是在不撞墙或不撞自身的情况下，抓住最大数量的水果。在学习 Python 或 Pygame 时，创建一个蛇游戏可以被视为一种挑战。这是最好的初学者友好项目之一，每个新手程序员都应该接受挑战。学习制作一个电子游戏是一种有趣的学习。

我们将使用 [**Pygame**](https://www.geeksforgeeks.org/introduction-to-pygame/) 来创建这个蛇游戏。 **Pygame** 是一个为制作电子游戏而设计的开源库。它有内置的图形和声音库。它也是初学者友好的，跨平台的。

### 装置

要安装 Pygame，您需要打开您的终端或命令提示符，并键入以下命令:

```
pip install pygame
```

在安装完 Pygame 之后，我们准备好创建我们的酷蛇游戏了。

### **使用 Pygame 创建蛇游戏的分步方法:**

**步骤 1:** 首先我们导入必要的库。

*   之后，我们将定义游戏窗口的宽度和高度。
*   并以 RGB 格式定义我们将在游戏中用于显示文本的颜色。

## 蟒蛇 3

```
# importing libraries
import pygame
import time
import random

snake_speed = 15

# Window size
window_x = 720
window_y = 480

# defining colors
black = pygame.Color(0, 0, 0)
white = pygame.Color(255, 255, 255)
red = pygame.Color(255, 0, 0)
green = pygame.Color(0, 255, 0)
blue = pygame.Color(0, 0, 255)
```

**第二步:**导入库后我们需要使用 **pygame.init()** 方法初始化 Pygame。

*   使用上一步定义的宽度和高度创建一个游戏窗口。
*   这里 **pygame.time.Clock()** 将在游戏的主逻辑中进一步使用来改变蛇的速度。

## 蟒蛇 3

```
# Initialising pygame
pygame.init()

# Initialise game window
pygame.display.set_caption('GeeksforGeeks Snakes')
game_window = pygame.display.set_mode((window_x, window_y))

# FPS (frames per second) controller
fps = pygame.time.Clock()
```

**第三步:**初始化蛇的位置和大小。

*   初始化蛇的位置后，在定义的高度和宽度的任何地方随机初始化水果的位置。
*   通过将方向设置为右，我们可以确保每当用户运行程序/游戏时，蛇必须向右移动到屏幕上。

## 蟒蛇 3

```
# defining snake default position
snake_position = [100, 50]

# defining first 4 blocks of snake
# body
snake_body = [  [100, 50],
                [90, 50],
                [80, 50],
                [70, 50]
            ]
# fruit position
fruit_position = [random.randrange(1, (window_x//10)) * 10,
                  random.randrange(1, (window_y//10)) * 10]
fruit_spawn = True

# setting default snake direction
# towards right
direction = 'RIGHT'
change_to = direction
```
# 蟒蛇中的红霞曲线和莫勒玫瑰

> 原文:[https://www . geesforgeks . org/rhodonea-curves-and-Maurer-rose-in-python/](https://www.geeksforgeeks.org/rhodonea-curves-and-maurer-rose-in-python/)

在本文中，我们将用 Python 创建一个 Rhodonea 曲线和 Maurer Rose 模式！在我们继续研究到底什么是*红呼吸曲线*或*莫勒玫瑰*之前，我们需要准备好我们程序的基本结构！

## 计划的基本结构–

在我们继续学习任何关于罗多尼亚曲线或莫勒玫瑰图案的知识之前，我们首先需要准备好程序的基本结构。因此，当我们重构代码时，我们将只修改一个函数，而程序的其余部分将保持不变。这是程序的基本结构–

## 蟒蛇 3

```
from math import sin
from math import cos
from math import radians

import pygame

# The width and height of our program
(width, height) = (800, 600)

# Setup the window and init the screen surface
screen = pygame.display.set_mode((width, height))

pygame.display.set_caption('Rose Curve in Python !')

# The background color of the screen
screen.fill((250, 250, 205)) # lemonChiffon color

# Our function for drawing the rose pattern
drawPattern()

# Flip the drawn canvas with the newly created canvas (double-buffering)
# Basically we're refreshing the screen surface after drawing
pygame.display.flip()

# Our Main Loop
while True :

    # Poll the events in the event queue
    for event in pygame.event.get() :

        # if the user closed the window
        if event.type == pygame.QUIT :

            # deactivate pygame and quit the program
            pygame.quit()  
            quit()

        # Draws the surface object to the screen. 
        pygame.display.update()
```
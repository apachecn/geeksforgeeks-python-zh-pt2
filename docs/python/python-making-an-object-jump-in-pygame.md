# Python |在 PyGame 中进行对象跳转

> 原文:[https://www . geesforgeks . org/python-制作对象-在 pygame 中跳转/](https://www.geeksforgeeks.org/python-making-an-object-jump-in-pygame/)

Pygame 是一套跨平台的 Python 模块，设计用于编写视频游戏。它包括设计用于 Python 编程语言的计算机图形和声音库。现在，这取决于开发者的想象力或必要性，他/她想使用这个工具包开发什么类型的游戏。
所以，在本文中，我们将学习如何使用 Python 中的 PyGame 库进行对象跳转。

经典力学中有使物体跳跃的基本公式。

```py
F = 1/2 * m * v^2 

```

其中 F 是向上/向下的力，m 是物体的质量，v 是速度。速度随着时间的推移而下降，因为在这个模拟中，当物体跳跃时，速度不会增加更多。当物体到达地面时，跳跃结束。如果`isjump` 变量为真或假，则表示对象是否在跳跃。如果`isjump` 为真，对象位置将根据上述公式更新。

Below is the implementation:

```py
# import pygame module in this program 
import pygame

# activate the pygame library . 
# initiate pygame and give permission 
# to use pygame's functionality. 
pygame.init()

# create the display surface object 
# of specific dimension..e(500, 500). 
win = pygame.display.set_mode((500, 500))

# set the pygame window name 
pygame.display.set_caption("Jump Game")

# object current co-ordinates
x = 200
y = 200

# dimensions of the object
width = 30
height = 40

# Stores if player is jumping or not
isjump = False

# Force (v) up and mass m.
v = 5
m = 1

# Indicates pygame is running
run = True

# infinite loop
while run:

    # completely fill the surface object 
    # with black colour 
    win.fill((0, 0, 0))

    # drawing object on screen which is rectangle here 
    pygame.draw.rect(win, (255, 0, 0), (x, y, width, height))

    # iterate over the list of Event objects 
    # that was returned by pygame.event.get() method. 
    for event in pygame.event.get():

        # if event object type is QUIT 
        # then quitting the pygame 
        # and program both. 
        if event.type == pygame.QUIT:

            # it will make exit the while loop
            run = False
    # stores keys pressed
    keys = pygame.key.get_pressed()

    if isjump == False:

        # if space bar is pressed
        if keys[pygame.K_SPACE]:

            # make isjump equal to True
            isjump = True

    if isjump :
        # calculate force (F). F = 1 / 2 * mass * velocity ^ 2.
        F =(1 / 2)*m*(v**2)

        # change in the y co-ordinate
        y-= F

        # decreasing velocity while going up and become negative while coming down
        v = v-1

        # object reached its maximum height
        if v<0:

            # negative sign is added to counter negative velocity
            m =-1

        # objected reaches its original state
        if v ==-6:

            # making isjump equal to false 
            isjump = False

            # setting original values to v and m
            v = 5
            m = 1

    # creates time delay of 10ms
    pygame.time.delay(10)

    # it refreshes the window
    pygame.display.update() 
# closes the pygame window    
pygame.quit()
```

**输出:**

<video class="wp-video-shortcode" id="video-379288-1" width="640" height="640" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200203223530/Jump-Game-03-02-2020-22_16_04.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200203223530/Jump-Game-03-02-2020-22_16_04.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200203223530/Jump-Game-03-02-2020-22_16_04.mp4)</video>
# Python–在 PyGame 中移动对象

> 原文:[https://www . geesforgeks . org/python-移动 pygame 中的对象/](https://www.geeksforgeeks.org/python-moving-an-object-in-pygame/)

Pygame 是一组跨平台的 Python 模块，旨在编写视频游戏。它包括设计用于 Python 编程语言的计算机图形和声音库。现在，这取决于开发者的想象力或必要性，他/她想使用这个工具包开发什么类型的游戏。

在本教程中，我们将学习如何移动对象，使其在按下键盘上的右箭头键或左箭头键时水平移动，而在按下上箭头键或下箭头键时垂直移动。

这样做的主要概念是通过改变物体的坐标和刷新屏幕。当屏幕每次刷新时，窗口颜色会被原始颜色填充，新的矩形会形成，因此当按下箭头键时，坐标会发生变化，对象似乎在移动。

```
Change in Co-ordinates for respective keys pressed :

Left arrow key: Decrement in x co-ordinate
Right arrow key: Increment in x co-ordinate
Up arrow key: Decrement in y co-ordinate
Down arrow key: Increment in y co-ordinate

```

下面是实现。

```
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
pygame.display.set_caption("Moving rectangle")

# object current co-ordinates 
x = 200
y = 200

# dimensions of the object 
width = 20
height = 20

# velocity / speed of movement
vel = 10

# Indicates pygame is running
run = True

# infinite loop 
while run:
    # creates time delay of 10ms 
    pygame.time.delay(10)

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

    # if left arrow key is pressed
    if keys[pygame.K_LEFT] and x>0:

        # decrement in x co-ordinate
        x -= vel

    # if left arrow key is pressed
    if keys[pygame.K_RIGHT] and x<500-width:

        # increment in x co-ordinate
        x += vel

    # if left arrow key is pressed   
    if keys[pygame.K_UP] and y>0:

        # decrement in y co-ordinate
        y -= vel

    # if left arrow key is pressed   
    if keys[pygame.K_DOWN] and y<500-height:
        # increment in y co-ordinate
        y += vel

    # completely fill the surface object  
    # with black colour  
    win.fill((0, 0, 0))

    # drawing object on screen which is rectangle here 
    pygame.draw.rect(win, (255, 0, 0), (x, y, width, height))

    # it refreshes the window
    pygame.display.update() 

# closes the pygame window 
pygame.quit()
```

**<video class="wp-video-shortcode" id="video-383628-1" width="640" height="640" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200227214935/Moving-rectangle-27-02-2020-21_46_05.mp4?_=1">[https://media . geekesforgeks . org/WP-content/uploads/20200227214935/moveing-rectangle-27-02-2020-21 _ 46 _ 05 . MP4](https://media.geeksforgeeks.org/wp-content/uploads/20200227214935/Moving-rectangle-27-02-2020-21_46_05.mp4)</video>**
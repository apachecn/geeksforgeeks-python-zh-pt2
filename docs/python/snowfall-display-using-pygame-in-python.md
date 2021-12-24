# 使用 Python 中 Pygame 的降雪显示

> 原文:[https://www . geesforgeks . org/snow-display-using-pygame-in-python/](https://www.geeksforgeeks.org/snowfall-display-using-pygame-in-python/)

不是每个人都亲眼目睹过降雪，但是等一下，如果你仅仅通过几行创意和编程就能在屏幕上看到降雪呢？

在开始话题之前，强烈建议修改 [Pygame 的基础知识。](https://www.geeksforgeeks.org/introduction-to-pygame/)

## 创造降雪的步骤

**1。导入模块**

首先，我们需要使用命令导入 Pygame 模块。

> 进口 pygame

此外，除了 Pygame，我们还需要随机模块。Python 有一个内置模块，你可以通过导入随机模块来生成随机数。

> 导入随机

**2。初始化游戏引擎**

它只是意味着选择你想要使用的颜色。在编程世界里，你认为你能做什么就做什么。在文章的最后，你会在白色背景上发现绿色的降雪。

## 蟒蛇 3

```py
# initialize
pygame.init()

# chosen colours will be used
# to display the output
WHITE = [255, 255, 255]
GREEN = [0, 255, 0]
```

**3。指定屏幕尺寸**

它可以是一个新的数字，具体取决于您系统的分辨率。

## 蟒蛇 3

```py
# specify the size

SIZE = [400, 400]
screen = pygame.display.set_mode(SIZE)
```

**4。给你的降雪窗口屏幕命名**

给定的名称可以在输出窗口的左上角看到。

## 蟒蛇 3

```py
# caption for output window

pygame.display.set_caption("Programming World of GFG")
```

**5。为你的降雪创建一个空数组**

## 蟒蛇 3

```py
snowFall = []
```

**6。循环获取降雪位置**

做一个循环，运行到 50 次，并使用随机模块在随机的 x，y 位置增加一场降雪。

## 蟒蛇 3

```py
for i in range(50):
    x = random.randrange(0, 400)
    y = random.randrange(0, 400)
    snowFall.append([x, y])
```
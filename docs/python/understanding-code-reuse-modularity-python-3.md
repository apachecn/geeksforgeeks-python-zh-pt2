# 理解 Python 3 中的代码重用和模块化

> 原文:[https://www . geesforgeks . org/understanding-code-重用-模块化-python-3/](https://www.geeksforgeeks.org/understanding-code-reuse-modularity-python-3/)

**什么是面向对象编程(OOP)？**

OOP 是一种基于“对象”概念的编程范式，它可能包含数据，形式为字段，通常称为属性；和代码，通常称为方法。在这里了解更多[，或者只需谷歌“OOP”。
物体有特征和特性，被称为属性，并且可以通过它们的方法做各种事情。OOP 最大的特点是对象可以很好地交互，甚至在未来被塑造，这使得它们对开发人员非常友好，可扩展，随时间变化，可测试，等等。](https://en.wikipedia.org/wiki/Object-oriented_programming) 

**什么是模块化？**

模块化是指先制作多个模块，然后将它们链接组合成一个完整的系统的概念(即一个软件/Web 应用程序可以划分成更小模块的程度称为模块化)。模块化能够实现可重用性，并将最大限度地减少重复。

**文章流程**

**目的:**学习面向对象编程——模块化。我们如何将代码的某些部分转换成一个库，以便任何人都可以使用它作为未来的参考。使代码模块化将实现可重用性并最大限度地减少重复。

**依赖关系:** pygame

**总结:**我们要做一个小游戏(其实不是游戏)，只是一个环境和里面的一些物体。我们将尝试使环境静态化，对象(在我们的例子中是斑点)模块化。我们将利用 PyGame，因为它为我们提供了一种简单的方式来实际可视化我们正在做什么和构建什么，这样我们就可以看到我们的对象在行动。我们要做的是建立 Blob World，这是一个由演员组成的世界，被称为 Blob。不同的斑点具有不同的属性，并且斑点需要在它们的斑点世界环境中运行。通过这个例子，我们将能够说明模块化。

我们将我们的学习过程分为两个阶段。

1.  创造环境和博客
2.  理解模块化

存储库(Github): [来源](https://github.com/SKKSaikia/GeeksforGeeks/tree/master/modularity)

**BLOB 世界(Python 代码)**

## 计算机编程语言

```
import pygame
import random

STARTING_BLUE_BLOBS = 10
STARTING_RED_BLOBS = 3

WIDTH = 800
HEIGHT = 600
WHITE = (255, 255, 255)
BLUE = (0, 0, 255)
RED = (255, 0, 0)

game_display = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Blob World")
clock = pygame.time.Clock()

class Blob:

    def __init__(self, color):
        self.x = random.randrange(0, WIDTH)
        self.y = random.randrange(0, HEIGHT)
        self.size = random.randrange(4,8)
        self.color = color

    def move(self):
        self.move_x = random.randrange(-1,2)
        self.move_y = random.randrange(-1,2)
        self.x += self.move_x
        self.y += self.move_y

        if self.x < 0: self.x = 0
        elif self.x > WIDTH: self.x = WIDTH

        if self.y < 0: self.y = 0
        elif self.y > HEIGHT: self.y = HEIGHT

def draw_environment(blob_list):
    game_display.fill(WHITE)

    for blob_dict in blob_list:
        for blob_id in blob_dict:
            blob = blob_dict[blob_id]
            pygame.draw.circle(game_display, blob.color, [blob.x, blob.y], blob.size)
            blob.move()

    pygame.display.update()

def main():
    blue_blobs = dict(enumerate([Blob(BLUE) for i in range(STARTING_BLUE_BLOBS)]))
    red_blobs = dict(enumerate([Blob(RED) for i in range(STARTING_RED_BLOBS)]))
    while True:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                quit()
        draw_environment([blue_blobs,red_blobs])
        clock.tick(60)

if __name__ == '__main__':
    main()
```

**输出:**

<video class="wp-video-shortcode" id="video-141933-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/bobWorld.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/bobWorld.mp4](https://media.geeksforgeeks.org/wp-content/uploads/bobWorld.mp4)</video>

**PART(1/2): Blob World** 在这一部分，我们正在创建一个简单的游戏环境和其中的一些对象，因为可视化我们所创建的是学习编程的一种特殊方式。使用 pygame 创建 blob 世界(即其环境和对象)的解释在这里[解释](https://drive.google.com/file/d/0ByqooCIGbyKiUEZYVlhjSWlsdVk/view?usp=sharing)。我们需要了解的是如何使我们的代码模块化。

**PART(2/2):模块化**在第二部分中，我们将了解面向对象编程的一个基本特征，即模块化。到目前为止，我们还没有引入任何会使这个(BLOB WORLD [代码](https://github.com/SKKSaikia/GeeksforGeeks/blob/master/modularity/blob_world.py))随着时间的推移变得太难维护或扩展的东西，至少在我们可以用 PyGame 做的范围内。把它做成模块化怎么样？对此有一个非常简单的测试，让我们尝试导入它！

为此，让我们有两个文件。让我们复制 Blob 类和 random，并创建一个新文件: [blob.py](https://github.com/SKKSaikia/GeeksforGeeks/blob/master/modularity/blob_1.py)

```
import random

class Blob:

    def __init__(self, color):
        self.x = random.randrange(0, WIDTH)
        self.y = random.randrange(0, HEIGHT)
        self.size = random.randrange(4,8)
        self.color = color

    def move(self):
        self.move_x = random.randrange(-1,2)
        self.move_y = random.randrange(-1,2)
        self.x += self.move_x
        self.y += self.move_y

        if self.x  WIDTH: self.x = WIDTH

        if self.y  HEIGHT: self.y = HEIGHT
```

回到我们的原始文件，让我们删除 Blob 类，然后从 blob.py 导入 Blob。

```
import pygame
import random
from blob import Blob

STARTING_BLUE_BLOBS = 10
...
```

马上，我们在 blob.py 文件中得到一个错误，关于我们的 blob 类，我们有一些未定义的变量。这绝对是编写类的问题，我们应该尽量避免在类外使用常量或变量。让我们将这些值添加到 __init__ 方法中，然后修改使用常量的所有部分。
这是我们新的 Blob 类文件: [blob.py](https://github.com/SKKSaikia/GeeksforGeeks/blob/master/modularity/blob.py)

接下来，在我们的原始文件中，当我们调用 Blob 类时，它需要这些参数的一些值，所以您应该在主函数中添加这些值:

```
def main():
    blue_blobs = dict(enumerate([Blob(BLUE,WIDTH,HEIGHT) for i in range(STARTING_BLUE_BLOBS)]))
    red_blobs = dict(enumerate([Blob(RED,WIDTH,HEIGHT) for i in range(STARTING_RED_BLOBS)]))
    while True:
        ...
```

太好了，所以现在我们的 Blob 类至少可以被导入，所以它本质上已经是模块化的了！另一个好主意是尝试给使用你的代码的开发人员尽可能多的权力，并使你的类尽可能的通用。至少有一个例子，我们可以给使用这个类的程序员更多的东西，那就是 blob 大小的定义:

```
  self.size = random.randrange(4,8) 
```

我们为什么不想给程序员一个简单的方法来改变这些呢？我不这么认为。然而，与 x_boundary 和 y_boundary 不同，我们不一定需要程序员为我们提供一个大小值，因为我们至少可以使用一个合理的起始默认值。因此，我们可以这样做:

```
class Blob:

    def __init__(self, color, x_boundary, y_boundary, size_range=(4,8)):
        self.x_boundary = x_boundary
        self.y_boundary = y_boundary
        self.x = random.randrange(0, self.x_boundary)
        self.y = random.randrange(0, self.y_boundary)
        self.size = random.randrange(size_range[0],size_range[1])
        self.color = color
```

现在，如果程序员想改变大小，他们可以，否则他们不必。我们可能还想允许程序员修改 blob 的速度，如果他们想:

```
import random

class Blob:

    def __init__(self, color, x_boundary, y_boundary, size_range=(4,8), movement_range=(-1,2)):
        self.size = random.randrange(size_range[0],size_range[1])
        self.color = color
        self.x_boundary = x_boundary
        self.y_boundary = y_boundary
        self.x = random.randrange(0, self.x_boundary)
        self.y = random.randrange(0, self.y_boundary)
        self.movement_range = movement_range

    def move(self):
        self.move_x = random.randrange(self.movement_range[0],self.movement_range[1])
        self.move_y = random.randrange(self.movement_range[0],self.movement_range[1])
        self.x += self.move_x
        self.y += self.move_y

        if self.x  self.x_boundary: self.x = self.x_boundary

        if self.y  self.y_boundary: self.y = self.y_boundary
```

现在我们已经开了很多课。我们还有什么问题吗？是的，我们强制斑点保持在边界内的线。有没有可能有这样的例子，我们希望这些斑点能够自由地在视野之外漫游？当然可以！这个边界代码有用吗？程序员是否有可能经常想利用这一点？当然可以！然而，更有意义的是要么根本没有代码，要么给它自己的方法，就像这样:

```
import random

class Blob:

    def __init__(self, color, x_boundary, y_boundary, size_range=(4,8), movement_range=(-1,2)):
        self.size = random.randrange(size_range[0],size_range[1])
        self.color = color
        self.x_boundary = x_boundary
        self.y_boundary = y_boundary
        self.x = random.randrange(0, self.x_boundary)
        self.y = random.randrange(0, self.y_boundary)
        self.movement_range = movement_range

    def move(self):
        self.move_x = random.randrange(self.movement_range[0],self.movement_range[1])
        self.move_y = random.randrange(self.movement_range[0],self.movement_range[1])
        self.x += self.move_x
        self.y += self.move_y

    def check_bounds(self):
        if self.x  self.x_boundary: self.x = self.x_boundary

        if self.y  self.y_boundary: self.y = self.y_boundary
```

现在，程序员可以决定是否使用它。您也可以在 move 方法中给出某种类型的参数，如果为 True，则将强制边界。
因此，我们了解了如何将 python 代码模块化。

**资源:**

*   [原创视频系列(pythonprogramming.net 出品)](https://www.youtube.com/playlist?list=PLIYU_0sc1XOA7OhuWwhDSAxnOZn4LDeTU)
*   [pythonprogramming.net](https://pythonprogramming.net/)
*   [哈里森·金斯利(谢谢 H .金斯利)](https://www.linkedin.com/in/hkinsley/)

本文由 **Amartya Ranjan Saikia** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
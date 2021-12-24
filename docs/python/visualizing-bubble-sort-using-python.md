# 使用 Python 可视化气泡排序

> 原文:[https://www . geeksforgeeks . org/visiting-bubble-sort-using-python/](https://www.geeksforgeeks.org/visualizing-bubble-sort-using-python/)

**先决条件:**[Matplotlib 简介](https://www.geeksforgeeks.org/python-introduction-matplotlib/)[PyQt5 简介](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/)[冒泡排序](https://www.geeksforgeeks.org/bubble-sort/)

学习任何算法都可能是困难的，既然你在极客伪造公司，你肯定喜欢理解和实现各种算法。对我们每个人来说，第一次理解算法是很难的。我们倾向于更好地理解那些形象化的事物。我们首先要解决的一个基本问题是排序算法。学习这些算法对你来说可能很有挑战性，所以今天我们向你展示如何可视化它们。

### 需要的模块

**Matplotlib:**Matplotlib 是 Python 中一个惊人的可视化库，用于数组的 2D 图。要安装，请在终端输入以下命令。

```py
pip install matplotlib
```

****pyqt 5:**pyqt 5 是跨平台的 GUI 工具包，一套针对 Qt v5 的 python 绑定。由于该库提供的工具和简单性，人们可以非常容易地开发交互式桌面应用程序。要安装它，请在终端中键入以下命令。**

```py
pip install PyQt5==5.9.2
```

**好了，我们开始实际编码吧。首先，创建一个名为 **main.py** 的文件，并向其中添加以下代码行。**

## **蟒蛇 3**

```py
# imports
import random
from matplotlib import pyplot as plt, animation

# helper methods
def swap(A, i, j):
    A[i], A[j] = A[j], A[i]

# algorithms
def bubblesort(A):
    swapped = True

    for i in range(len(A) - 1):
        if not swapped:
            return
        swapped = False

        for j in range(len(A) - 1 - i):
            if A[j] > A[j + 1]:
                swap(A, j, j + 1)
                swapped = True
            yield A

def visualize():
    N = 30
    A = list(range(1, N + 1))
    random.shuffle(A)

    # creates a generator object containing all 
    # the states of the array while performing 
    # sorting algorithm
    generator = bubblesort(A)

    # creates a figure and subsequent subplots
    fig, ax = plt.subplots()
    ax.set_title("Bubble Sort O(n\N{SUPERSCRIPT TWO})")
    bar_sub = ax.bar(range(len(A)), A, align="edge")

    # sets the maximum limit for the x-axis
    ax.set_xlim(0, N)
    text = ax.text(0.02, 0.95, "", transform=ax.transAxes)
    iteration = [0]

    # helper function to update each frame in plot
    def update(A, rects, iteration):
        for rect, val in zip(rects, A):
            rect.set_height(val)
        iteration[0] += 1
        text.set_text(f"# of operations: {iteration[0]}")

    # creating animation object for rendering the iteration
    anim = animation.FuncAnimation(
        fig,
        func=update,
        fargs=(bar_sub, iteration),
        frames=generator,
        repeat=True,
        blit=False,
        interval=15,
        save_count=90000,
    )

    # for showing the animation on screen
    plt.show()
    plt.close()

if __name__ == "__main__":
    visualize()
```

****输出:****

**<video class="wp-video-shortcode" id="video-495961-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201004005059/output1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201004005059/output1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201004005059/output1.mp4)</video>**
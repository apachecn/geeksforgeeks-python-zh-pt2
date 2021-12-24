# Python–在 kivy 中舍入按钮角

> 原文:[https://www . geesforgeks . org/python-rounding-button-corners-in-kivy/](https://www.geeksforgeeks.org/python-rounding-button-corners-in-kivy/)

Kivy 是 Python 中独立于平台的 GUI 工具。因为它可以在安卓、IOS、Linux 和视窗等平台上运行。它基本上是用来开发安卓应用的，但并不意味着它不能在桌面应用上使用。

在本文中，我们将学习如何在 kivy python 中舍入按钮角。

现在出现了一个问题——在 kivy 中为按钮创建圆角的首选方法是什么？

基本上，这是个棘手的问题。正如我们所知**小部件**总是一个**矩形**，但是我们可以改变小部件的背景，通过使用按钮的一些属性，比如 background_normal 和 background_down 属性，分别为按钮的正常和向下状态放置一些图像。
同样为了圆化按钮的角，您还必须了解按钮的另一个属性，即边框属性。

> **background_down :**
> 1)按钮的背景图像，用于按钮按下时的默认图形表示。
> 2) background_down 是 StringProperty。
> 
> **background_normal :**
> 1)按钮的背景图像，用于按钮未被按下时的默认图形表示。
> 2) background_normal 也是 StringProperty。
> 
> **边框:**
> 1)边框用于边框图形指令。与 background_normal 和 background_down 一起使用。可用于自定义背景。
> 2)必须是四个值的列表:(下、右、上、左)。
> 3)边框为列表属性，默认为(16，16，16，16)

> [**Kivy 教程——用例子学习 Kivy。**T3】](https://www.geeksforgeeks.org/kivy-tutorial/)

**上述所有属性的语法:**

## 蟒蛇 3

```py
background_normal: 'normal.png'
background_down: 'down.png'
border: 30, 30, 30, 30
```
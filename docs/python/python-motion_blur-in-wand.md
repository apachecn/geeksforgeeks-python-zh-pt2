# Python–魔杖中的运动模糊()

> 原文:[https://www.geeksforgeeks.org/python-motion_blur-in-wand/](https://www.geeksforgeeks.org/python-motion_blur-in-wand/)

我们可以在魔杖中执行的另一种模糊是**运动模糊**。在这种情况下，高斯模糊是在一个单一的线性方向上执行的，它看起来像是图像在线性方向上移动。它采用了一个新的角度参数。

> **语法:**
> 
> ## 蟒蛇 3
> 
> ```
> wand.image.motion_blur(radius= radius_value, sigma= sigma_value,
>              angle= angle_value, channel = "optional_channel_value")
> # radius should always be greater than sigma(standard deviation)
> ```
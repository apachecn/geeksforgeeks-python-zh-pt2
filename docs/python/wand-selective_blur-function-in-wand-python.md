# 魔杖 python 中的魔杖选择性 _ 模糊()功能

> 原文:[https://www . geesforgeks . org/魔杖-选择性 _ 模糊-魔杖中的功能-python/](https://www.geeksforgeeks.org/wand-selective_blur-function-in-wand-python/)

另一种可以使用 python 中的魔杖库执行的模糊是选择性模糊。选择性模糊类似于正常模糊。不同之处在于，它只影响图像中对比度低于给定量子阈值的部分。这个函数中引入了一个名为 threshold 的新属性。

> **语法:**
> 
> ## 蟒蛇 3
> 
> ```
> wand.image.selective_blur(radius= radius_value, sigma= sigma_value,
>                           threshold= thrshold_value,
>                           channel = "optional_channel_value")
>  
> # radius should always be greater than sigma(standard deviation)
> ```
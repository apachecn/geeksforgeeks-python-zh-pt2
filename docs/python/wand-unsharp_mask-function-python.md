# 魔杖反锐化掩模()功能–Python

> 原文:[https://www . geesforgeks . org/wand-unsharpp _ mask-function-python/](https://www.geeksforgeeks.org/wand-unsharp_mask-function-python/)

**unsharp_mask()** 类似于 python Wand 中的普通锐化()方法，但它给出了在滤镜和原始(数量参数)之间进行锐化的控制，以及阈值。当数量值大于 1.0 时，如果应用了锐化滤镜，则增加；如果值小于 1.0，则减少。阈值超过 0.0 会降低锐化。

> **语法:**
> 
> ## 蟒蛇 3
> 
> ```py
> wand.image.unsharp_mask(radius, sigma, amount, threshold)
> ```
# Python 中社交计算的概念

> 原文:[https://www . geeksforgeeks . org/python 中的社交计算概念/](https://www.geeksforgeeks.org/the-concept-of-social-computing-in-python/)

当你尝试在谷歌上搜索一些你可能想知道的事情，或者只是想回忆一些事情，例如，如果你试图记住一首你之前听过但回忆不起来的歌，只有你能记得这首歌是在哪里拍摄的，那么你可能不会通过谷歌找到它，你可以做的是写一篇文章并在社交媒体上分享。如果你朋友圈子里有人知道这件事，会给你答案。你可能找到答案，也可能找不到。但是，如果有很多人回答了你的问题，其中一个人是答案，这意味着你只需要在社交媒体上分享你的问题就可以得到答案。所以我们可以说很多普通人的力量战胜了一个专业人士的力量。
社交计算的概念来了，像 Quora、StackOverflow 等很多网站都在使用这个概念。

#### 人群的智慧

根据群体智慧的概念，当许多人猜测一件事时，他们很有可能猜对了。这是因为有些人可能低估了它，有些人可能高估了它，所以这是**的意思**接近准确的答案。

基于**低估抵消了**高估的部分。

**修剪平均值的计算:**

*   计算总人群的 10%。
*   从列表中删除计算值的数量，即低估值的 10%和高估值的 10%。
*   现在计算平均值。

下面是实现。

## 蟒蛇 3

```
# Python program to demonstrate
# social computing

from statistics import mean

# Estimation provided by various
# users
Estimates = [1000, 1010, 1223, 52223, 2411,
             322, 563, 1246, 1000, 2333, 4666, 2133]

Estimates.sort()

tv = int(0.1 * len(Estimates))

# Removing Underestimating value
Estimates = Estimates[tv:]

# Removing overestimating value
Estimates = Estimates[:len(Estimates)-tv]

print(mean(Estimates))
```

**输出:**

```
1758.5
```
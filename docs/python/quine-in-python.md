# Python 中的奎因

> 原文:[https://www.geeksforgeeks.org/quine-in-python/](https://www.geeksforgeeks.org/quine-in-python/)

[蒯因](https://www.geeksforgeeks.org/quine-a-self-reproducing-program)是一个不接受输入但输出自己代码副本的程序。我们已经讨论了 C 中的[奎因。](https://www.geeksforgeeks.org/quine-a-self-reproducing-program/)

python 中最短的 quine 只是一行代码！

```
_='_=%r;print _%%_';print _%_
```

在 Python3.x 的情况下

```
_='_=%r;print (_%%_)';print (_%_)
```

**说明:**
以上代码是字符串格式的经典用法。首先，我们定义一个变量 *_* 并赋予它' _ = % r；print _%%_ '。其次，我们正在打印 *_%_* 。这里我们打印 _ with _ 作为字符串格式的输入。所以 _ 中的 *%r* 得到的值是 _。甚至可以用 *%s* 代替 *%r* 。我们在' _=%r 中使用了双*%*；print _%%_ '退出 *%* 。

但是你可能会说下面的代码是最小的，对吧！

```
print open(__file__).read()
```

你需要注意的是，它确实是可以打印自己源代码的最小的 python 程序，但它不是一个 quine，因为一个 quine 不应该使用 *open()* 函数打印出自己的源代码。

本文由**斯里·桑凯·乌帕拉帕蒂**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
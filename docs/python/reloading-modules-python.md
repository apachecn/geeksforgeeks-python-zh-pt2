# 在 Python 中重载模块

> 原文:[https://www.geeksforgeeks.org/reloading-modules-python/](https://www.geeksforgeeks.org/reloading-modules-python/)

**重装()**重装先前导入的模块。如果您已经使用外部编辑器编辑了模块源文件，并且希望在不离开 Python 解释器的情况下试用新版本，这将非常有用。返回值是模块对象。

**注意**:参数应该是已经成功导入的模块。

用法:

对于 Python2.x

```
reload(*module*)

```

对于 2.x 以上和< =Python3.3

```
import imp
imp.reload(*module*)

```

对于> =Python3.4

```
import importlib
importlib.reload(*module*)

```

有关更多信息，请查看 [reload()](https://docs.python.org/3/library/importlib.html#importlib.reload) 。

本文由**斯里·桑凯·乌帕拉帕蒂**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
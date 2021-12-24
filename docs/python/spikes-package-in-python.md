# Python 中的钉钉包

> 原文:[https://www.geeksforgeeks.org/spikes-package-in-python/](https://www.geeksforgeeks.org/spikes-package-in-python/)

[](https://pypi.org/project/spikes/)**是 Python 中的一个包，一个用于在终端显示条形图的命令行工具，因此可以用于快速分析**

****安装:**在终端上运行以下 pip 命令:**

```py
pip install spikes
```

**建议在 IDE 终端运行所有程序，因为 PowerShell 不支持很少的输出字符**

> ****语法:**尖峰[空格分隔数据]**

****示例 1:** 获取终端上整数的简单条形图**

```py
spike 10 20 30 40 50 60
```

****输出:****

**![](img/ffb08cd02e3b3bddb9b392b88092186a.png)**

****例 2:** 数据也可以是十进制数。**

```py
spike 0 1 2 0.3 0.4 0.5 6
```

****输出:****

**![](img/091652f66f2fa2f66736efe363684ddc.png)**

****例 3:** 如果数据为负值，(必须有第一个值为正值)，则认为它们为零，并显示图形的正值**

```py
spike 2 -7 -9
spike -2 -7 9
```

****输出:****

**![](img/9227cab5a8d75f868bc5d174b0e2a895.png)**

****示例 4:** 对于垂直数据，在开头使用-1 标志。**

```py
spike -1 5 10 17 29
```

****输出:****

**![](img/131152bb0c472c58a0490d6bef7eb47b.png)**
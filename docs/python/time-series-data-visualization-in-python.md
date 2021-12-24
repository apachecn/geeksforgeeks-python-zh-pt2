# Python 中的时间序列数据可视化

> 原文:[https://www . geesforgeks . org/time-series-data-visualization-in-python/](https://www.geeksforgeeks.org/time-series-data-visualization-in-python/)

时间序列是按时间顺序列出的一系列数据点。时间序列是一系列连续的等间隔时间点。时间序列分析包括分析时间序列数据的方法，以便提取有意义的见解和数据的其他有用特征。时间序列数据分析在许多行业变得非常重要，如金融行业、制药、社交媒体公司、网络服务提供商、研究等。为了理解时间序列数据，可视化是必不可少的。没有可视化，任何类型的数据分析都是不完整的。因为一个好的可视化可以为数据提供有意义和有趣的见解。

做任何类型的数据分析数据集都是最重要和最基本的要求。没有数据集，我们就无法进行分析。这里我们正在为时间序列数据可视化收集股票数据。[点击这里](https://github.com/Neelu-Tiwari/dataset/blob/main/stock_data.csv)查看完整的数据集。为了可视化时间序列数据，我们需要导入一些包:

## python 3

```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
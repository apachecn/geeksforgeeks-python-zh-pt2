# Python 程序在心脏上显示任何消息

> 原文:[https://www . geesforgeks . org/python-program-display-any-message-on-heart/](https://www.geeksforgeeks.org/python-program-display-any-message-on-heart/)

本文重点讨论如何画一颗带有美好信息的心给你爱的人，表达你对他们的感受。这里将讨论上述问题陈述的三种变体:

*   Hearts with news.
*   Message from hearts.
*   The pink heart conveys information in different fonts and colors from the above two cases.

**程序 1:** 下面是简单红心的 python 代码，并附带一条消息:

## python 3

```
# Python3 program for the above approach
# import library
import pylab
import numpy as np

# Width of heart
Xaxis = np.linspace(-2, 2, 
                    100000)

# Setting upper y 
Y1axis = np.sqrt(1 - 
         (abs(Xaxis) - 1) **2)

# Setting -y
Y2axis = -3 * np.sqrt(1 - 
         (abs(Xaxis) / 2) **0.5)

# Adjust colour for upper part 
# of herat
pylab.fill_between(Xaxis, Y1axis, 
                   color = 'red')

# Adjust colour for lower part 
# of heart
pylab.fill_between(Xaxis, Y2axis, 
                   color = 'red')

pylab.xlim([-2.5, 2.5])
pylab.axis("off")

# Driver Code
text = "Geeksforgeeks"

pylab.text(0, -0.4, text, 
           fontsize = 24, 
           fontweight = 'bold',
           color = 'white', 
           horizontalalignment = 'center')
```
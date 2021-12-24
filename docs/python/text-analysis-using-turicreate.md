# 使用 Turicreate 进行文本分析

> 原文:[https://www . geeksforgeeks . org/text-analysis-using-turi create/](https://www.geeksforgeeks.org/text-analysis-using-turicreate/)

**什么是文本分析？**
文本是一组单词或句子。文本分析是对文本进行分析，然后借助文本提取信息。文本数据是决定公司大小的最大因素之一。例如

*   在电子商务网站上，人们买东西。通过文本分析，电子商务网站可以知道客户喜欢什么，并通过这些数据提高生产力。
*   使用文本分析和一些机器学习算法，我们的 Alexa 谷歌主页迷你作品。这两个是基于自然语言处理。
*   使用文本分析，我们可以确定电子邮件是垃圾邮件还是非垃圾邮件。

文本分析可以使用文本挖掘来完成。因为文本“数据”可以是结构化的，也可以是非结构化的。文本挖掘技术将帮助我们区分它们。

现在让我们使用图创建做一些文本分析。我们将建立一个模型，将邮件分类为垃圾邮件或火腿，用于文本分析。数据集链接=[https://www . kaggle . com/team-ai/spam-text-message-classing](https://www.kaggle.com/team-ai/spam-text-message-classification)
**第一步:导入图创建库**

## 蟒蛇 3

```py
import turicreate as tc
```
# Python 硒–通过文本查找元素

> 原文:[https://www . geesforgeks . org/python-selenium-按文本查找元素/](https://www.geeksforgeeks.org/python-selenium-find-element-by-text/)

验证用户给出的需求是否符合实际开发的软件产品的技术称为**软件测试**。此外，它还检查最终开发的软件产品是否没有错误。软件测试可以手动进行，也可以借助软件测试工具进行。通过内置工具自动完成的测试被称为**自动化测试。**一个不可思议的 Python 库，Selenium 帮助您实现软件的自动化测试。在进行自动化测试时，您是否无法在所需的网页中通过文本找到元素？然后，你在一个合适的地方。在本文中，我们将讨论适当的步骤，并给出一个例子来实现同样的目的。

> **语法:**driver . find _ element _ by _ XPath("//标记[包含(text()，' word')]")
> 
> **参数:**
> 
> *   **标签:**这里，标签代表包含特定单词的标签名称。
> *   **word:** 这里，word 代表必须在特定字符串中找到的文本。我们不需要写一个我们想找的完整句子，但是我们可以写几个在网页中独一无二的单词。

**示例:**例如，考虑这个简单的页面源:

## 超文本标记语言

```py
<!DOCTYPE html>
<html> 
<body> 
<button type= “button” >Geeks For Geeks</button> 
</body> 
<html>
```

创建驱动程序后，您可以使用以下方法来掌握元素:

> button = driver . find _ element _ by _ XPath("//button[包含(text()，' Geeks 代表 Geeks')]")

### 让我们通过实现来理解这一点:

**步骤 1:** 首先，导入库、硒和时间。

## 计算机编程语言

```py
from selenium import webdriver
from time import sleep
```

**步骤 3:** 接下来，通过可执行路径与 web 驱动建立连接。

## 蟒蛇 3

```py
driver = webdriver.Chrome(
    executable_path="#path where you have installed webdriver")
```
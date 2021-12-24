# 使用 Python 中的 selenium . select _ by _ visible _ text()方法选择下拉列表

> 原文:[https://www . geesforgeks . org/select-a-下拉列表-通过使用-selenium-select _ by _ visible _ text-method-in-python/](https://www.geeksforgeeks.org/selecting-a-drop-down-list-by-using-the-selenium-select_by_visible_text-method-in-python/)

硒是通过程序控制互联网浏览器的有效设备。它对所有浏览器都是有目的的，适用于所有基本操作系统，其脚本是用许多语言编写的，如 Python、Java、C#等，我们可以用 Python 运行。

**选择类的不同方法:**

*   按 INDEX 从下拉菜单中选择一个选项。
*   **通过可见文本从下拉列表中选择一个选项。**
*   按值从下拉菜单中选择一个选项。

我们正在讨论下拉列表中的可见文本方法。

该策略通过其明显的选择标签来选择替代方案。它承认选择标签的明显的内容估计，并且不返回任何东西。

**要求:**需要安装 chromedriver 并设置路径。[**点击此处**](https://sites.google.com/a/chromium.org/chromedriver/downloads) 下载，更多信息请点击[**此链接**。](https://www.geeksforgeeks.org/browser-automation-using-selenium/)

**使用下拉列表:**最初，您必须导入选择类，然后您必须创建选择类的案例。在选择类的情况下，您可以在该场合执行选择策略，从下拉列表中选择选项。

> 从 selenium.webdriver.support.ui 导入选择

通过使用进行选择

> drop = Select(driver . find _ element _ by _ id(')
> 
> drop.select_by_visible_text(" ")

**示例:**我们将执行以下操作:

*   进口硒模块
*   导入选择类模块
*   使用网页进行下拉列表 [**(网址**](https://fs2.formsite.com/meherpavan/form2/index.html?1537702596407) )。
*   导航到选项栏的 id。

![](img/2c060435ee20a546aa1972d1a04ab2d5.png)

## 蟒蛇 3

```py
# importing the modules
from selenium import webdriver
from selenium.webdriver.support.ui import Select
import time

# using chrome driver
driver=webdriver.Chrome()

# web page url
driver.get("https://fs2.formsite.com/meherpavan/form2/index.html?1537702596407")

# find id of option
x = driver.find_element_by_id('RESULT_RadioButton-9')
drop=Select(x)

# select by visible text
drop.select_by_visible_text("Afternoon")
time.sleep(4)
driver.close()
```

**输出:**

<video class="wp-video-shortcode" id="video-493683-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200925012101/by-visible.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200925012101/by-visible.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200925012101/by-visible.mp4)</video>
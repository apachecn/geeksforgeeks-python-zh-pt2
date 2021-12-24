# Python 程序寻找使用特定编程语言的 GSoC 组织

> 原文:[https://www . geesforgeks . org/python-program-to-find-gsoc-使用特定编程语言的组织/](https://www.geeksforgeeks.org/python-program-to-find-gsoc-organisations-that-use-a-particular-programming-language/)

目前，无法按照 GSoC 参与组织在代码中使用的编程语言对其进行排序。这导致学生花费大量时间浏览每个组织的页面，并手动对它们进行排序。

本文介绍了一种让学生使用 BeautifulSoup4 库编写自己的 **Python 脚本**的方法。使用这个脚本，学生可以找到使用他们想要贡献的语言的组织。

**通过这篇文章你会学到以下内容:**

*   如何使用请求库向网页发送 HTTPS 请求
*   如何用 python 中的美化程序库解析 HTML 代码
*   使用 OpenPyXL 以电子表格(如 MS Excel)的形式输出数据

#### 装置

上述模块没有预装 Python。要安装它们，请在终端中键入以下命令。

```py
pip install requests
pip install beautifulsoup4
pip install openpyxl
```

**注意:**跟随这篇文章只需要 Python 3 的初级知识。更多信息，请参考 [Python 编程语言](https://www.geeksforgeeks.org/python-programming-language/)

#### 入门指南

**步骤 1:** 导入所需的库

```py
import requests, bs4, openpyxl
```

**步骤 2:** 使用请求创建响应对象。我们将使用存档页面作为我们的来源

```py
# Replace "YEAR" by the year you
#  want to get data from. Eg. "2018"
url = 'https://summerofcode.withgoogle.com/archive/YEAR/organizations/'

# Creating a response object 
# from the given url
res = requests.get(url)

# We'll be using the Archive page
# of GSoC's website as our source.
# Checking the url's status
res.raise_for_status()
```

**步骤 3:** 创建一个漂亮的耦合对象

从存档页面的源代码:

```py
<li class="organization-card__container"
    layout
    flex-xs="100"
    flex-sm="50"
    flex="33"
    aria-label="AerospaceResearch.net">
    ...
        ...
    <div class="organization-card__footer md-padding">

        <h4 class="organization-card__name font-black-54">AerospaceResearch.net</h4>

    </div>
    ...
        ...
</li>
```

我们可以看到组织的名字在一个名为“`organization-card__name font-black-54`”的`H4`标签中。

使用 BS4，我们可以在 HTML 代码中搜索这个特定的标签，并将文本存储在列表中。

```py
# Specify the language you
#  want to search for
language = 'python'

# BS4 object to store the 
# html text We use res.text 
# to get the html code in text format
soup = bs4.BeautifulSoup(res.text, 'html.parser')

# Selecting the specific tag 
# with class name
orgElem = soup.select('h4[class ="organization-card__name font-black-54"]')

# Similarly finding the links 
# for each org's gsoc page
orgLink = soup.find_all("a", class_="organization-card__link")
languageCheck = ['no'] * len(orgElem)
orgURL = ['none'] * len(orgElem)
```

**第 4 步:**打开每个组织的 GSoC 页面，找到使用的语言

```py
item = 0
# Loop to go through each organisation
for link in orgLink:

    # Gets the anchor tag's hyperlink
    presentLink = link.get('href') 

    url2 = 'https://summerofcode.withgoogle.com' + presentLink 
    print(item)
    print(url2)
    orgURL[item] = url2
    res2 = requests.get(url2)
    res2.raise_for_status()

    soup2 = bs4.BeautifulSoup(res2.text, 'html.parser')
    tech = soup2.find_all("li",
                      class_="organization__tag organization__tag--technology")

    # Finding if the org uses 
    # the specified language
    for name in tech:

        if language in name.getText():
            languageCheck[item] = 'yes'

    item = item + 1
```

**第 5 步:**将列表写入电子表格

使用`openpyxl`库，我们首先创建一个工作簿。在本工作簿中，我们使用 wb['Sheet']打开一个工作表，实际上我们将在其中写入数据。使用`cell().value`功能，我们可以直接向每个单元格写入值。最后我们使用`save()`功能保存工作簿。

```py
wb = openpyxl.Workbook()
sheet = wb['Sheet']

for i in range(0, len(orgElem)):
    sheet.cell(row = i + 1, column = 1).value = orgElem[i].getText()
    sheet.cell(row = i + 1, column = 2).value = languageCheck[i]
    sheet.cell(row = i + 1, column = 3).value = orgURL[i]

wb.save('gsocOrgsList.xlsx')
```

**注意:**电子表格将存储在与 Python 文件相同的目录中

#### 解决纷争

由于对网站的重复请求，服务器可能会在多次尝试后阻止您的 IP 地址。使用虚拟专用网将解决这个问题。
如果问题仍然存在，请在代码中添加以下内容:

```py
from fake_useragent import UserAgent

ua = UserAgent()
header = {
    "User-Agent": ua.random
     }
```
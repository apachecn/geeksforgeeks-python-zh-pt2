# 用漂亮的包解析表格和 XML

> 原文:[https://www . geeksforgeeks . org/parsing-tables-and-XML-with-beautulsoup/](https://www.geeksforgeeks.org/parsing-tables-and-xml-with-beautifulsoup/)

**额外优惠:** [美汤刮痧](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)[XML 解析](https://www.geeksforgeeks.org/xml-parsing-python/)

抓取是每个人都应该学习的一项非常重要的技能，它帮助我们从网站或文件中抓取数据，程序员可以用另一种漂亮的方式使用这些数据。在本文中，我们将学习如何从网站中提取一个表，并从文件中提取 XML。
在这里，我们将使用美汤 Python 模块废弃数据。

**所需模块:**

*   **bs4:** 美人汤是一个从 HTML 和 XML 文件中拉出数据的 Python 库。可以使用以下命令安装:

```py
pip install bs4
```

*   **lxml:** 它是一个 Python 库，允许我们处理 xml 和 HTML 文件。可以使用以下命令安装:

```py
pip install lxml
```

*   **请求:** Requests 可以让你极其轻松地发送 HTTP/1.1 请求。可以使用以下命令安装:

```py
pip install request
```

### 解析表的分步方法:

**第一步:**首先我们需要导入模块，然后分配 URL。

## 蟒蛇 3

```py
# import required modules
import bs4 as bs
import requests

# assign URL
URL = 'https://www.geeksforgeeks.org/python-list/'
```

**第二步:**创建一个*的*对象进行解析。

## 蟒蛇 3

```py
# parsing
url_link = requests.get(URL)
file = bs.BeautifulSoup(url_link.text, "lxml")
```

**第三步:**然后找到表及其行。

## 蟒蛇 3

```py
# find all tables
find_table = file.find('table', class_='numpy-table')
rows = find_table.find_all('tr')
```

**第 4 步:**现在创建一个循环，查找表中所有的 *td* 标签，然后打印所有的表数据标签。

## 蟒蛇 3

```py
# display tables
for i in rows:
    table_data = i.find_all('td')
    data = [j.text for j in table_data]
    print(data)
```
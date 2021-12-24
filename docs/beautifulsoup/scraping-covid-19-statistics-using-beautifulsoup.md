# 使用美丽组

刮除新冠肺炎统计

> 原文:[https://www . geeksforgeeks . org/scratch-新冠肺炎-统计-使用-美化组/](https://www.geeksforgeeks.org/scraping-covid-19-statistics-using-beautifulsoup/)

冠状病毒，疫情最大的病毒之一，已经把全世界都带到了危险之中。与此同时，这是一个趋势新闻，每个人都有这一天。在本文中，我们将以人类可读的形式抓取数据并打印新冠肺炎统计数据。数据将从[本网站](https://www.worldometers.info/coronavirus/countries-where-coronavirus-has-spread/)
**刮取先决条件:**

*   必须安装库“请求”、“bs4”和“texttable”–

```
pip install bs4
pip install requests
pip install texttable

```

**项目:**让我们开始编码，创建一个名为 run.py 的文件

## 蟒蛇 3

```
# importing modules
import requests
from bs4 import BeautifulSoup

# URL for scrapping data
url = 'https://www.worldometers.info/coronavirus/countries-where-coronavirus-has-spread/'

# get URL html
page = requests.get(url)
soup = BeautifulSoup(page.text, 'html.parser')

data = []

# soup.find_all('td') will scrape every
# element in the url's table
data_iterator = iter(soup.find_all('td'))

# data_iterator is the iterator of the table
# This loop will keep repeating till there is
# data available in the iterator
while True:
    try:
        country = next(data_iterator).text
        confirmed = next(data_iterator).text
        deaths = next(data_iterator).text
        continent = next(data_iterator).text

        # For 'confirmed' and 'deaths',
        # make sure to remove the commas
        # and convert to int
        data.append((
            country,
            int(confirmed.replace(', ', '')),
            int(deaths.replace(', ', '')),
            continent
        ))

    # StopIteration error is raised when
    # there are no more elements left to
    # iterate through
    except StopIteration:
        break

# Sort the data by the number of confirmed cases
data.sort(key = lambda row: row[1], reverse = True)
```
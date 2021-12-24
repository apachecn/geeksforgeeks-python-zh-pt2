# 如何使用美丽的组合刮除嵌套标签？

> 原文:[https://www . geesforgeks . org/how-to-scratch-nested-tags-using-beauty ulsup/](https://www.geeksforgeeks.org/how-to-scrape-nested-tags-using-beautifulsoup/)

在的帮助下，我们可以在漂亮的汤里扔掉嵌套标签。(点)运算符。在创建了一个汤的页面后，如果我们想导航嵌套标签，那么借助。我们能做到。要使用“美丽组”抓取嵌套标签，请遵循以下步骤。

### 逐步方法

**第一步:**第一步是抓取我们需要导入的美丽的请求模块，获取我们需要导入请求模块的网站的请求。

```
from bs4 import BeautifulSoup
import requests
```

**第二步:**第二步将请求 URL 调用 get 方法。

```
page=requests.get(sample_website)
```

**第三步:**第三步是创建一个使用漂亮的输出方法的汤，对于 HTML 解析树，使用一个 HTML 解析器。

```
BeautifulSoup(page.content, 'html.parser')
```

**第四步:**第四步将执行。操作符直到当我们想要标记为废弃嵌套标记时，如果我们想要废弃主体和表内的标记，那么我们将使用下面的语句来废弃嵌套标记。

```
soup.body.table.tag
```

### 履行

以下是描述如何从特定[网址](https://www.geeksforgeeks.org/different-ways-to-remove-all-the-digits-from-string-in-java/)中抓取不同嵌套标签的各种示例

**例 1:**

## 蟒蛇 3

```
from bs4 import BeautifulSoup
import requests

# sample website
sample_website = 'https://www.geeksforgeeks.org/different-ways-to-remove-all-the-digits-from-string-in-java/'

# call get method to request the page
page = requests.get(sample_website)

# with the help of BeautifulSoup method and
# html parser created soup
soup = BeautifulSoup(page.content, 'html.parser')

# With the help of . operator we will scrap a tag
# under body->ui->i
# here we will go a tag inside body then ul then
# i.means under the body tag we will go to ul tag
# and again inside the ul tag we will go i tag
print(soup.body.ul.i)
```

**输出:**

```
<i class="gfg-icon gfg-icon_arrow-down gfg-icon_header"></i>
```

**例 2:**

## 蟒蛇 3

```
from bs4 import BeautifulSoup
import requests

# sample website
sample_website = 'https://www.geeksforgeeks.org/different-ways-to-remove-all-the-digits-from-string-in-java/'

# call get method to request the page
page = requests.get(sample_website)

# with the help of BeautifulSoup method and html
# parser created soup
soup = BeautifulSoup(page.content, 'html.parser')

# With the help of . operator we will scrap a tag
# under body->a
# here we will go a tag inside body then a then
# li.means under the body tag we will go to a tag
print(soup.body.a)
```

**输出:**

```
<a class="gfg-stc" href="#main" style="top:0">Skip to content</a>
```

**例 3:**

## 蟒蛇 3

```
from bs4 import BeautifulSoup
import requests

# sample website
sample_website = 'https://www.geeksforgeeks.org/different-ways-to-remove-all-the-digits-from-string-in-java/'

# call get method to request the page
page = requests.get(sample_website)

# with the help of BeautifulSoup method and
# html parser created soup
soup = BeautifulSoup(page.content, 'html.parser')

#With the help of . operator we will scrap a
# tag under body->a
# here we will go a tag inside body then a then
# li.means under the body tag we will go to a tag 
print(soup.body.a)

# With the help of . operator we will scrap a
# tag under body->ui->li
# here we will go a tag inside body then ul then
# li.means under the body tag we will go to ul tag
# and again inside the ul tag we will go li tag
# and inside to li tag we will go to a tag
print(soup.body.ul.li.a)
```

**输出:**

> [渐近分析](”https://www.geeksforgeeks.org/analysis-of-algorithms-set-1-asymptotic-analysis/”)
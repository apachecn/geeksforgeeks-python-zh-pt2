# Python–使用 beauty sup

获取 YouTube 视频的标题、视图和赞

> 原文:[https://www . geeksforgeeks . org/python-获取标题-查看和喜欢-YouTube-视频-使用-美化程序/](https://www.geeksforgeeks.org/python-obtain-title-views-and-likes-of-youtube-video-using-beautifulsoup/)

在本文中，我们将学习如何使用 Python 脚本从任何 YouTube 视频中获取数据(如标题、视图、好恶等)。对于这个任务，我们将使用非常著名的库来进行网页抓取和请求。

**所需模块和安装:**

> **[Requests](https://www.geeksforgeeks.org/python-requests-tutorial/):**
> Requests 可以让你极其轻松地发送 HTTP/1.1 请求。没有必要手动添加查询字符串到你的网址。
> 
> ```
> pip install requests
> ```
> 
> **[【美人汤】T2:](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)**
> 美人汤是一个可以轻松从网页上抓取信息的库。它位于 HTML 或 XML 解析器之上，为迭代、搜索和修改解析树提供了 Pythonic 习惯用法。
> 
> ```
> pip install beautifulsoup4
> ```

对于给定的视频网址，将进行数据抓取。然后数据的解析(标题、视图、赞元素)将使用美汤的`find()`方法完成。它会在字典中找到并存储这些值。

**代码:**

```
# importing the libraries
from bs4 import BeautifulSoup
import requests

# creating function
def scrape_info(url):

    # getting the request from url
    r = requests.get(url)

    # converting the text
    s = BeautifulSoup(r.text, "html.parser")

    # finding meta info for title
    title = s.find("span", class_="watch-title").text.replace("\n", "")

    # finding meta info for views
    views = s.find("div", class_="watch-view-count").text

    # finding meta info for likes
    likes = s.find("span", class_="like-button-renderer").span.button.text

    # saving this data in dictionary
    data = {'title':title, 'views':views, 'likes':likes}

    # returning the dictionary
    return data

# main function
if __name__ == "__main__":

    # URL of the video
    url ="https://www.youtube.com/watch?time_continue=17&v=2wEA8nuThj8"

    # calling the function
    data = scrape_info(url)

    # printing the dictionary
    print(data)
```

**输出:**

> { ' title ':' placement 100 | geeks forgeeks '，' view ':' 18，964 views '，' like ':' 37 ' }
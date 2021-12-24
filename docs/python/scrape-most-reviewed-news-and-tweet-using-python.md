# 用 Python 抓取评论最多的新闻和推文

> 原文:[https://www . geeksforgeeks . org/scrap-最多评论-新闻和推文-使用-python/](https://www.geeksforgeeks.org/scrape-most-reviewed-news-and-tweet-using-python/)

许多网站将提供任何技术的时尚新闻，文章可以通过评论数量进行评级。假设新闻是针对加密货币的，新闻文章是从[cointelegraph.com](https://cointelegraph.com/category/latest-news)刮来的，我们可以让每个新闻项评论者轻松统计，放入 MongoDB 收藏。

### 需要的模块

*   **Tweepy:** Tweepy 是官方推特 API 的 Python 客户端。使用以下 pip 命令进行安装:

    ```
    pip install tweepy
    ```

*   **MongoClient:**MongoClient 类使人们能够用您的代码成功地建立 MongoDB 服务器连接。使用以下 pip 命令进行安装:

    ```
    pip install pymongo
    ```

*   **pyshortners:**pyshortners 用于以编程方式缩短、标记、共享或检索链接中的数据。通过以下方式安装

    ```
    pip install pyshorteners
    ```

### 证明

为了通过推特应用编程接口获取推文，人们需要通过他们的推特账户注册一个应用程序。遵循以下步骤:

*   打开此链接[https://apps.twitter.com/](https://apps.twitter.com/)并点击按钮:“创建新应用”
*   填写申请详情。您可以将回调 url 字段留空。
*   应用程序创建后，您将被重定向到应用程序页面。
*   打开“密钥和访问令牌”选项卡。
*   复制“消费者密钥”、“消费者秘密”、“访问令牌”和“访问令牌秘密”，并将其粘贴到下面的代码中。

下面是实现。

```
# Python program to get top 3 trendy news item 

import tweepy
import json
from datetime import date, timedelta, datetime
from pymongo import MongoClient
from html.parser import HTMLParser
import re
from pyshorteners import Shortener

NewsArrayIndex = 0
NewsArray = [None] * 3

class MyHTMLParser(HTMLParser):

    # This function collects the value
    # of href and stores in NewsArrayIndex 
    # variable
    def handle_starttag(self, tag, attrs):

        # Only parse the 'anchor' tag.
        global NewsArrayIndex
        if tag == "a":

            # Check the list of defined attributes.
            for name, value in attrs:

                # If href is defined, print it.
                if name == "href":

                    # print(value + "\t" + News1)                                   
                    NewsArray[NewsArrayIndex] = value

                    # print(NewsArray)
                    NewsArrayIndex += 1

# This function is the primary place
# to tweet the collected daily news
# News is retrieved from Coll_DailyNewsPlusReview 
# collection (MongoDB collection) This collection
# holds the value of "News Headlines, Its review 
# count, news link" and based upon the review count,
# top most # reviewed news are taken As twitter allows
# only 280 characters, the retrieved news link got
# shortened by using BITLY API Hashtags related to
# the news are added underneath the retrieved top
# 3 news (All together allowed characters are 280)
# Then top 3 news gets tweeted from a credential
# Finally per day basis the tweeted news are stored
# into another collection for audit purpose as well
# as for weekly posting
def tweetDailyNews():

    try:

        # This is the collection name in mongodb
        cursor_P = db1.Coll_DailyNewsPlusReview.find({"time": date_str})

        p0 = cursor_P[0]
        News = p0.get('News')
        sortedNews = sorted(News, key = lambda x: int(x[1]), reverse = True)
        print(sortedNews[0][0]+"--" + sortedNews[0][1],
              sortedNews[1][0] + ".."+ sortedNews[1][1],
              sortedNews[2][0] + ".." + sortedNews[2][1])

        hyperlink_format = '<a href ="{link}">{text}</a>'
        parser = MyHTMLParser()
        dailyNews = "Impactful News of the Day" + "\n"

        News0 = sortedNews[0][2]
        parser.feed(hyperlink_format.format(link = News0, text = News0))

        News1 = sortedNews[1][2]
        print("News1", News1)
        parser.feed(hyperlink_format.format(link = News1, text = News1))

        News2 = sortedNews[2][2]
        print(News2)
        parser.feed(hyperlink_format.format(link = News2, text = News2))

        # News shortening pattern
        BITLY_ACCESS_TOKEN ="20dab258cc44c7d017bcd1c1f4b24484a37b8de9"
        b = Shortener(api_key = ACCESS_TOKEN) 

        NewsArray[0] = re.sub('\n', '', NewsArray[0])
        response1 = b.bitly.short(NewsArray[0]) 
        response1 = response1['url']

        NewsArray[1] = re.sub('\n', '', NewsArray[1])
        response2 = b.bitly.short(NewsArray[1]) 
        response2 = response2['url']

        NewsArray[2] = re.sub('\n', '', NewsArray[2])
        response3 = b.bitly.short(NewsArray[2]) 
        response3 = response3['url']

        news1FewWords = sortedNews[0][0].split()
        dailyNews += news1FewWords[0] + " " 
        + news1FewWords[1] + " " + news1FewWords[2] 
        + "...." + response1 + "\n"

        news2FewWords = sortedNews[1][0].split()
        dailyNews += news2FewWords[0] + " " 
        + news2FewWords[1] + " " + news2FewWords[2] 
        + "...." + response2+"\n"

        news3FewWords = sortedNews[2][0].split()
        dailyNews += news3FewWords[0] + " " 
        + news3FewWords[1] + " " + news3FewWords[2]
        + "...." + response3 + "\n" + "# bitcoin \
        # cryptocurrency # blockchain # investor # altcoins\
        # fintech # investment"
        print(dailyNews)

        status = api.update_status(status = dailyNews)
        if status:
            for i in range(3):
                datas = {}
                datas['time'] = str(date.today())
                datas['posted_as'] = i
                datas['news'] = sortedNews[i][0]
                datas['shortenedlink'] = NewsArray[i]
                datas['reviewcount'] = sortedNews[i][1]
                datas['link'] = sortedNews[i][2]
                db1.Collection_tweeted_news.insert(datas)

    except Exception as e:
        print(e)
        print("Error in getting today news data", str(date_str))

# Driver Code
News1 = ' '
News2 = ' '

date_str = str(date.today())
print("today", date_str)
client = MongoClient('mongodb://localhost:27017/')

# Connect your database here
db1 = client.xxxx 

# credentials to tweet
consumer_key ="xxxx"
consumer_secret ="xxxx"
access_token ="xxxx"
access_token_secret ="xxxx"

# authentication of consumer key and secret 
auth = tweepy.OAuthHandler(consumer_key, consumer_secret) 

# authentication of access token and secret 
auth.set_access_token(access_token, access_token_secret) 
api = tweepy.API(auth,
                 wait_on_rate_limit = True,
                 wait_on_rate_limit_notify = True)   

tweetDailyNews()
```

**输出:**

> 资深投资者表示。https://bit.ly/2X1x51V
> 比特币有水滴。https://bit.ly/2T83xyS
> 那个……的风投。https://bit.ly/3czxVKb
> #比特币#加密货币#区块链#投资者#奥币#金融科技#投资
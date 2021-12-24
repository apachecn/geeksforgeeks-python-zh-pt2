# 使用 Python 进行推特情感分析

> 原文:[https://www . geesforgeks . org/Twitter-情绪-分析-使用-python/](https://www.geeksforgeeks.org/twitter-sentiment-analysis-using-python/)

本文通过使用 Python 解析从推特获取的推文，涵盖了任何主题的情感分析。

![](img/ae53084d12a871fda3c61653f4903b3a.png)

**什么是情绪分析？** 情绪分析是“计算”确定一篇文章是正面、负面还是中性的过程。它也被称为**观点挖掘**，从说话者的观点或态度中获取信息。

**为什么要进行情绪分析？**

*   **商业:**在营销领域，公司利用它来制定策略，了解客户对产品或品牌的感受，人们如何回应他们的活动或产品发布，以及为什么消费者不购买一些
    产品。
*   **政治:**在政治领域，用于跟踪政治观点，检测政府层面的言论和行动之间的一致性和不一致性。它也可以用来预测选举结果！
*   **公众行动:**情绪分析还用于监控和分析社会现象，以发现潜在的危险情况，并确定博客圈的总体情绪。

**安装:**

*   **Tweepy:** [tweepy](http://docs.tweepy.org/en/v3.5.0/) 是官方[推特 API](https://dev.twitter.com/rest/public) 的 python 客户端。
    使用以下 pip 命令进行安装:

    ```
    pip install tweepy
    ```

*   **TextBlob:** [textblob](http://textblob.readthedocs.io/en/dev/) is the python library for processing textual data.
    Install it using following pip command:

    ```
    pip install textblob
    ```

    此外，我们需要使用以下命令安装一些 NLTK 语料库:

    ```
    python -m textblob.download_corpora
    ```

    (语料库不过是一大套结构化的文本。)

**认证:** 为了通过推特 API 获取推文，需要通过自己的推特账号注册 App。遵循以下步骤:

*   打开此[链接](https://apps.twitter.com/)并点击按钮:‘创建新应用’
*   填写申请详情。您可以将回调 url 字段留空。
*   应用程序创建后，您将被重定向到应用程序页面。
*   打开“密钥和访问令牌”选项卡。
*   复制“消费者密钥”、“消费者秘密”、“访问令牌”和“访问令牌秘密”。

**实施:**

```
import re
import tweepy
from tweepy import OAuthHandler
from textblob import TextBlob

class TwitterClient(object):
    '''
    Generic Twitter Class for sentiment analysis.
    '''
    def __init__(self):
        '''
        Class constructor or initialization method.
        '''
        # keys and tokens from the Twitter Dev Console
        consumer_key = 'XXXXXXXXXXXXXXXXXXXXXXXX'
        consumer_secret = 'XXXXXXXXXXXXXXXXXXXXXXXXXXXX'
        access_token = 'XXXXXXXXXXXXXXXXXXXXXXXXXXXX'
        access_token_secret = 'XXXXXXXXXXXXXXXXXXXXXXXXX'

        # attempt authentication
        try:
            # create OAuthHandler object
            self.auth = OAuthHandler(consumer_key, consumer_secret)
            # set access token and secret
            self.auth.set_access_token(access_token, access_token_secret)
            # create tweepy API object to fetch tweets
            self.api = tweepy.API(self.auth)
        except:
            print("Error: Authentication Failed")

    def clean_tweet(self, tweet):
        '''
        Utility function to clean tweet text by removing links, special characters
        using simple regex statements.
        '''
        return ' '.join(re.sub("(@[A-Za-z0-9]+)|([^0-9A-Za-z \t])
                                    |(\w+:\/\/\S+)", " ", tweet).split())

    def get_tweet_sentiment(self, tweet):
        '''
        Utility function to classify sentiment of passed tweet
        using textblob's sentiment method
        '''
        # create TextBlob object of passed tweet text
        analysis = TextBlob(self.clean_tweet(tweet))
        # set sentiment
        if analysis.sentiment.polarity > 0:
            return 'positive'
        elif analysis.sentiment.polarity == 0:
            return 'neutral'
        else:
            return 'negative'

    def get_tweets(self, query, count = 10):
        '''
        Main function to fetch tweets and parse them.
        '''
        # empty list to store parsed tweets
        tweets = []

        try:
            # call twitter api to fetch tweets
            fetched_tweets = self.api.search(q = query, count = count)

            # parsing tweets one by one
            for tweet in fetched_tweets:
                # empty dictionary to store required params of a tweet
                parsed_tweet = {}

                # saving text of tweet
                parsed_tweet['text'] = tweet.text
                # saving sentiment of tweet
                parsed_tweet['sentiment'] = self.get_tweet_sentiment(tweet.text)

                # appending parsed tweet to tweets list
                if tweet.retweet_count > 0:
                    # if tweet has retweets, ensure that it is appended only once
                    if parsed_tweet not in tweets:
                        tweets.append(parsed_tweet)
                else:
                    tweets.append(parsed_tweet)

            # return parsed tweets
            return tweets

        except tweepy.TweepError as e:
            # print error (if any)
            print("Error : " + str(e))

def main():
    # creating object of TwitterClient Class
    api = TwitterClient()
    # calling function to get tweets
    tweets = api.get_tweets(query = 'Donald Trump', count = 200)

    # picking positive tweets from tweets
    ptweets = [tweet for tweet in tweets if tweet['sentiment'] == 'positive']
    # percentage of positive tweets
    print("Positive tweets percentage: {} %".format(100*len(ptweets)/len(tweets)))
    # picking negative tweets from tweets
    ntweets = [tweet for tweet in tweets if tweet['sentiment'] == 'negative']
    # percentage of negative tweets
    print("Negative tweets percentage: {} %".format(100*len(ntweets)/len(tweets)))
    # percentage of neutral tweets
    print("Neutral tweets percentage: {} % \
        ".format(100*(len(tweets) -(len( ntweets )+len( ptweets)))/len(tweets)))

    # printing first 5 positive tweets
    print("\n\nPositive tweets:")
    for tweet in ptweets[:10]:
        print(tweet['text'])

    # printing first 5 negative tweets
    print("\n\nNegative tweets:")
    for tweet in ntweets[:10]:
        print(tweet['text'])

if __name__ == "__main__":
    # calling main function
    main()
```

以下是运行上述程序时示例输出的样子:

```
Positive tweets percentage: 22 %
Negative tweets percentage: 15 %

Positive tweets:
RT @JohnGGalt: Amazing—after years of attacking Donald Trump the media managed
to turn #InaugurationDay into all about themselves.
#MakeAme…
RT @vooda1: CNN Declines to Air White House Press Conference Live YES! 
THANK YOU @CNN FOR NOT LEGITIMI…
RT @Muheeb_Shawwa: Donald J. Trump's speech sounded eerily familiar...
POTUS plans new deal for UK as Theresa May to be first foreign leader to meet new 
president since inauguration 
.@realdonaldtrump #Syria #Mexico #Russia & now #Afghanistan. 
Another #DearDonaldTrump Letter worth a read @AJEnglish 

Negative tweets:
RT @Slate: Donald Trump’s administration: “Government by the worst men.” 
RT @RVAwonk: Trump, Sean Spicer, et al. lie for a reason. 
Their lies are not just lies. Their lies are authoritarian propaganda.  
RT @KomptonMusic: Me: I hate corn 
Donald Trump: I hate corn too
Me: https://t.co/GPgy8R8HB5
It's ridiculous that people are more annoyed at this than Donald Trump's sexism.
RT @tony_broach: Chris Wallace on Fox news right now talking crap 
about Donald Trump news conference it seems he can't face the truth eithe…
RT @fravel: With False Claims, Donald Trump Attacks Media on Crowd Turnout 
Aziz Ansari Just Hit Donald Trump Hard In An Epic Saturday NIght Live Monologue
```

我们在计划中遵循以下 3 个主要步骤:

*   授权推特 API 客户端。
*   向推特应用编程接口发出获取请求，为特定查询获取推文。
*   解析推文。将每条推文分为正面、负面或中性。

现在，让我们试着理解上面这段代码:

*   首先，我们创建一个**推特客户端**类。这个类包含了所有与 Twitter API 交互和解析推文的方法。我们使用 **__init__** 函数来处理 API 客户端的认证。
*   In **get_tweets** function, we use:

    ```
    fetched_tweets = self.api.search(q = query, count = count)
    ```

    调用推特应用编程接口来获取推文。

*   In **get_tweet_sentiment** we use textblob module.

    ```
    analysis = TextBlob(self.clean_tweet(tweet))
    ```

    TextBlob 实际上是一个建立在 [NLTK](http://www.nltk.org/) 库之上的高级库。首先我们调用 **clean_tweet** 方法移除链接、特殊字符等。使用一些简单的正则表达式。
    然后，当我们通过**推文**来创建**文本块**对象时，通过文本块库对文本进行以下处理:

    *   标记推文，即从正文中拆分单词。
    *   从令牌中删除 stopwords。(stopwords 是文本分析中不相关的常用词，如 I、am、you、are 等。)
    *   对标记进行词性标注，只选择形容词、副词等重要特征/标记。
    *   将令牌传递给**情感分类器**，该分类器通过为推文情感指定-1.0 到 1.0 之间的极性，将推文情感分类为正面、负面或中性。

    以下是**情感分类器**的创建过程:

    *   **文本块**使用电影评论数据集，其中评论已经被标记为正面或负面。
    *   正面和负面特征分别从每个正面和负面评论中提取。
    *   训练数据现在由标记的正面和负面特征组成。该数据在[朴素贝叶斯分类器](https://en.wikipedia.org/wiki/Naive_Bayes_classifier)上训练。

    然后，我们使用**文本 Blob** 类的**情绪.极性**方法，得到推文的极性在-1 到 1 之间。
    然后，我们把极性分类为:

    ```
    if analysis.sentiment.polarity > 0:
           return 'positive'
    elif analysis.sentiment.polarity == 0:
           return 'neutral'
    else:
           return 'negative'
    ```

*   最后，返回解析后的推文。然后，我们可以对推文进行各种类型的统计分析。例如，在上面的程序中，我们试图找到关于查询的正面、负面和中性推文的百分比。

**参考文献:**

*   [http://www . ijcaonline . org/research/volume 125/number 3/dandrea-2015-ijca-905866 . pdf](http://www.ijcaonline.org/research/volume125/number3/dandrea-2015-ijca-905866.pdf)
*   [https://text blob . read the docs . io/en/dev/quick start . html #情绪分析](https://textblob.readthedocs.io/en/dev/quickstart.html#sentiment-analysis)
*   [text ob . readthedocs . io/en/dev/_ modules/text ob/en/feelings . html](http://textblob.readthedocs.io/en/dev/_modules/textblob/en/sentiments.html)

本文由**尼克尔·库马尔**供稿。如果你喜欢极客博客并想投稿，你也可以用 write.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
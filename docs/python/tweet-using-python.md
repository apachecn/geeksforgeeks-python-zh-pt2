# 使用 Python 发推

> 原文:[https://www.geeksforgeeks.org/tweet-using-python/](https://www.geeksforgeeks.org/tweet-using-python/)

推特是一种在线新闻和社交网络服务，用户可以在这里发布消息并与之互动。这些帖子被称为“推文”。推特被称为机器人的社交媒体网站。我们甚至不用打开网站就可以用 Python 发布推文。有一个 Python 库，用于访问 Python 应用编程接口，称为 tweepy。在这里，我们将使用 tweepy 来做同样的事情。
Tweepy 不是原生库。使用前需要安装。安装很容易，当你有 pip。在终端或命令提示符下，键入以下命令安装 tweepy。

```
sudo install pip tweepy

```

如果您没有 pip，请将其安装为外部库。
不要忘记在设置中将应用类型从“只读”更改为“读写”。这也给了推特的许可。
之后，前往[https://apps.twitter.com/](https://apps.twitter.com/)。这是用来创建你的脚本和推特之间的链接。在“密钥和访问令牌”选项卡中，获取消费者密钥(应用编程接口密钥)、消费者秘密(应用编程接口秘密)、访问令牌和访问令牌秘密。

### 发布一条简单的推文

```
# importing the module
import tweepy

# personal details
consumer_key ="xxxxxxxxxxxxxxxx"
consumer_secret ="xxxxxxxxxxxxxxxx"
access_token ="xxxxxxxxxxxxxxxx"
access_token_secret ="xxxxxxxxxxxxxxxx"

# authentication of consumer key and secret
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)

# authentication of access token and secret
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth)

# update the status
api.update_status(status ="Hello Everyone !")
```

这是设置推文“大家好”的简单方法。这是一个简单的过程，在现实生活中并不重要。为了一些有用的工作，它被集成到更大的程序中。我们可以用 for 循环来发大量的推文。为了保持循环中任意两条推文之间的时间段，我们可以使用时间模块中的 sleep()函数，如图所示。

```
time.sleep(600) # waits for 600 seconds
```

这一切都是为了发布一条文字推文。如果我们想发布带有媒体文件的推文，有一个单独的方法。

### 发布带有媒体文件的推文

有时，用户想要发布带有媒体文件的推文，如果我们使用网站界面，这是非常简单的。在 Python 的帮助下发帖需要一些努力。这和发布只有两行代码的纯文本推文一样。

```
# importing the module
import tweepy

# personal information
consumer_key ="xxxxxxxxxxxxxxxx"
consumer_secret ="xxxxxxxxxxxxxxxx"
access_token ="xxxxxxxxxxxxxxxx"
access_token_secret ="xxxxxxxxxxxxxxxx"

# authentication
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)

api = tweepy.API(auth)
tweet ="Text part of the tweet" # toDo
image_path ="path of the image" # toDo

# to attach the media file
status = api.update_with_media(image_path, tweet) 
api.update_status(status = tweet)
```

请不要忘记如上所述更改应用程序类型。如果不改变它，我们就不能访问帖子。

本文由 [**里沙布·班萨尔**](https://www.linkedin.com/in/rishabh-bansal-9b4b71108/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
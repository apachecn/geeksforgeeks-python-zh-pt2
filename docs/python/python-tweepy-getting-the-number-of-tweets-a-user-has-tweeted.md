# Python Tweepy–获取用户已发推文的数量

> 原文:[https://www . geesforgeks . org/python-tweepy-get-tweet-number-a-user-tweet-tweet/](https://www.geeksforgeeks.org/python-tweepy-getting-the-number-of-tweets-a-user-has-tweeted/)

在这篇文章中，我们将看到我们如何获得用户已发推/更新的状态/推文数量。statuses _ count 属性为我们提供了一个整数，它表示用户已发布的状态数。

**识别用户在 GUI 中创建的日期:**
![](img/6afcbf3c22c53cb83f2061e89b3f1ec5.png)

在上面提到的配置文件中，用户发布的状态数:13.2K (13，200+)

> 为了获得用户发布的状态数，我们必须执行以下操作:
> 
> 1.  识别用户标识或配置文件的屏幕名称。
> 2.  使用带有用户标识或屏幕名称的`get_user()`方法获取配置文件的用户对象。
> 3.  从该对象中，获取其中存在的 statuses _ count 属性。

**示例 1:** 考虑以下配置文件:
![](img/6132b5064bacde4339adf720ea88d2db.png)
我们将使用用户 ID 来获取用户。上述配置文件的用户标识为 57741058。

```py
# import the module
import tweepy

# assign the values accordingly
consumer_key = ""
consumer_secret = ""
access_token = ""
access_token_secret = ""

# authorization of consumer key and consumer secret
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)

# set access to user's access key and access secret 
auth.set_access_token(access_token, access_token_secret)

# calling the api 
api = tweepy.API(auth)

# the ID of the user
id = 57741058

# fetching the user
user = api.get_user(id)

# fetching the statuses_count attribute
statuses_count = user.statuses_count 

print("The number of statuses the user has posted are : " + str(statuses_count))
```

**输出:**

```py
The number of statuses the user has posted are : 13239

```

**示例 2:** 考虑以下配置文件:
![](img/159935125f6fbd011d182156efb24f04.png)
我们将使用屏幕名称来获取用户。上面提到的配置文件的屏幕名称是 PracticeGfG。

```py
# the screen name of the user
screen_name = "PracticeGfG"

# fetching the user
user = api.get_user(screen_name)

# fetching the statuses_count attribute
statuses_count = user.statuses_count 

print("The number of statuses the user has posted are : " + str(statuses_count))
```

**输出:**

```py
The number of statuses the user has posted are : 2265

```
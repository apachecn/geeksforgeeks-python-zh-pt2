# Python Tweepy–获得推文被偏爱的次数

> 原文:[https://www . geeksforgeeks . org/python-tweepy-get-tweet-tweet-tweet-tweet-tweet-tweet-tweet-tweet-tweet-tweet-tweet-tweet-tweet-tweet-tweet-tweet-tweet-twee](https://www.geeksforgeeks.org/python-tweepy-getting-the-number-of-times-a-tweet-has-been-favourited/)

在本文中，我们将了解如何获得推文/状态被偏爱的次数。Status 对象的收藏夹 _ 计数属性为我们提供了一条推文被偏爱的次数。

**识别一条推文在 GUI 中被偏爱的次数:**
![](img/a2cf04d996c91bb12e836a619db040f4.png)

上述身份已被偏爱 16 次。

> 为了获得某个状态被偏爱的次数，我们必须执行以下操作:
> 
> 1.  从图形用户界面识别状态的状态标识。
> 2.  使用带有状态标识的`get_status()`方法获取状态的状态对象。
> 3.  从该对象中，获取其中存在的收藏夹 _ 计数属性。

**例 1 :** 考虑以下状态:
![](img/b66484537992670523a54c9ba241fbc4.png)

我们将使用状态标识来获取状态。上述状态的状态标识为 1272771459249844224。

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

# the ID of the status
id = 1272771459249844224

# fetching the status
status = api.get_status(id)

# fetching the favorite_count attribute
favorite_count = status.favorite_count

print("The number of time the status has been favourited is : " + str(favorite_count))
```

**输出:**

```py
The number of time the status has been favourited is : 17

```

**例 2 :** 考虑以下状态:
![](img/2893ea6f1652da3e4645b0bed573f047.png)

我们将使用状态标识来获取状态。上述状态的状态标识为 1272479136133627905。

```py
# the ID of the status
id = 1272479136133627905

# fetching the status
status = api.get_status(id)

# fetching the favorite_count attribute
favorite_count = status.favorite_count

print("The number of time the status has been favourited is : " + str(favorite_count))
```

**输出:**

```py
The number of time the status has been favorited is : 19

```
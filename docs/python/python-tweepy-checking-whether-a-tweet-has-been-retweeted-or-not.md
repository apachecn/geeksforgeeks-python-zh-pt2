# Python Tweepy–检查推文是否被转发

> 原文:[https://www . geesforgeks . org/python-tweepy-checking-a-tweet-tweet-是否已被转发/](https://www.geeksforgeeks.org/python-tweepy-checking-whether-a-tweet-has-been-retweeted-or-not/)

在本文中，我们将看到我们如何检查一条推文/状态是否被认证的用户转发。“状态”对象的“转发”属性指示该状态是否已被经过身份验证的用户转发。

**在 GUI 中识别已认证用户是否转发了状态:**
![](img/094f97f09bd7977ab259c30827849ac9.png)

在上面提到的状态中，转发图标是绿色的，因此经过身份验证的用户已经转发了推文。

> 为了检查经过身份验证的用户是否转发了状态，我们必须执行以下操作:
> 
> 1.  从图形用户界面识别状态的状态标识。
> 2.  使用带有状态标识的`get_status()`方法获取状态的状态对象。
> 3.  从该对象中，获取其中存在的转发属性。

**例 1 :** 考虑以下状态:
![](img/b66484537992670523a54c9ba241fbc4.png)

我们将使用状态标识来获取状态。上述状态的状态标识为 1272771459249844224。

```
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

# fetching the retweeted attribute
retweeted = status.retweeted 

if retweeted == True:
    print("The authenticated user has retweeted the tweet.")
else:
    print("The authenticated user has not retweeted the tweet.")
```

**输出:**

```
The authenticated user has not retweeted the tweet.

```

**例 2 :** 考虑以下状态:
![](img/2893ea6f1652da3e4645b0bed573f047.png)

我们将使用状态标识来获取状态。上述状态的状态标识为 1272479136133627905。

```
# the ID of the status
id = 1272479136133627905

# fetching the status
status = api.get_status(id)

# fetching the retweeted attribute
retweeted = status.retweeted 

if retweeted == True:
    print("The authenticated user has retweeted the tweet.")
else:
    print("The authenticated user has not retweeted the tweet.")
```

**输出:**

```
The authenticated user has retweeted the tweet.

```
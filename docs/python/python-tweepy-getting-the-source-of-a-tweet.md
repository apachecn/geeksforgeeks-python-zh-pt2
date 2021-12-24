# Python Tweepy–获取推文来源

> 原文:[https://www . geesforgeks . org/python-tweepy-get-source-of-tweet/](https://www.geeksforgeeks.org/python-tweepy-getting-the-source-of-a-tweet/)

在本文中，我们将了解如何获取状态/推文的来源。推文的来源告诉我们推文是如何发布的。来源的一些例子有:

*   安卓推特
*   iPhone 的推特
*   推特网络应用

状态对象的源属性为我们提供了状态的源。

**在 GUI 中识别状态的来源:**
![](img/869ec1d8342c766a5be8eb7b6ae5209c.png)

在上面提到的状态中，状态的来源是:安卓的推特

> 为了获取状态的来源，我们必须执行以下操作:
> 
> 1.  从图形用户界面识别状态的状态标识。
> 2.  使用带有状态标识的`get_status()`方法获取状态的状态对象。
> 3.  从该对象中，获取其中存在的源属性。

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

# fetching the source attribute
source = status.source 

print("The source of the status is : " + source)
```

**输出:**

```py
The source of the status is : Twitter for Android

```

**例 2 :** 考虑以下状态:
![](img/c58e0d641b7e97f9ee181110bab8b1d6.png)

我们将使用状态标识来获取状态。上述状态的状态标识为 1273112322773581824。

```py
# the ID of the status
id = 1273112322773581824

# fetching the status
status = api.get_status(id

# fetching the source attribute
source = status.source 

print("The source of the status is : " + source)
```

**输出:**

```py
The source of the status is : Twitter Web App

```
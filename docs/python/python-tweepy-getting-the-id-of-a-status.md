# Python Tweepy–获取状态的标识

> 原文:[https://www . geesforgeks . org/python-tweepy-get-id-of-a-status/](https://www.geeksforgeeks.org/python-tweepy-getting-the-id-of-a-status/)

在本文中，我们将了解如何获取状态的标识。每个状态或推文都有一个唯一的标识。Status 对象的 id 属性为我们提供了状态/推文的 ID。

**在图形用户界面中识别身份:**
![](img/362f74a165e93c29405d13f447ea691c.png)

在上述状态下，可以在网址中找到该标识，这里的标识是:1271031982189879297

> 为了获得状态的标识，我们必须执行以下操作:
> 
> 1.  从图形用户界面识别状态的状态标识。
> 2.  使用带有状态标识的`get_status()`方法获取状态的状态对象。
> 3.  从这个对象中，获取其中存在的 id 属性。

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

# fetching the id attribute
id = status.id 

print("The ID of the status is : " + str(id))
```

**输出:**

```
The ID of the status is : 1272771459249844224

```

**例 2 :** 考虑以下状态:
![](img/2893ea6f1652da3e4645b0bed573f047.png)

我们将使用状态标识来获取状态。上述状态的状态标识为 1272479136133627905。

```
# the ID of the status
id = 1272479136133627905

# fetching the status
status = api.get_status(id)

# fetching the id attribute
id = status.id 

print("The ID of the status is : " + str(id))
```

**输出:**

```
The ID of the status is : 1272479136133627905

```
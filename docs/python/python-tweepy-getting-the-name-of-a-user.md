# Python Tweepy–获取用户名称

> 原文:[https://www . geesforgeks . org/python-tweepy-get-用户名/](https://www.geeksforgeeks.org/python-tweepy-getting-the-name-of-a-user/)

在本文中，我们将了解如何获取用户名。Name 是 twitter 帐户的显示名称。它是用户选择在网络上用来表明自己身份的名称。许多用户选择使用真实姓名作为显示姓名的基础。与屏幕名称不同，名称不必是唯一的。此外，名称可以是任何语言的脚本，屏幕名称只能是英语(拉丁语)。名称中也可以有空格和特殊字符。

**在图形用户界面中识别名称:**
![](img/6dab3a690062ad61a2201d67b15ccbb1.png)

在上面提到的配置文件中，GeeksforGeeks 是配置文件的名称。

> 为了获得该名称，我们必须执行以下操作:
> 
> 1.  标识配置文件的用户标识或屏幕名称。
> 2.  使用带有用户标识或屏幕名称的`get_user()`方法获取配置文件的用户对象。
> 3.  从该对象中，获取其中存在的名称属性。

**示例 1:** 考虑以下配置文件:
![](img/6132b5064bacde4339adf720ea88d2db.png)
我们将使用用户 ID 来获取用户。上述配置文件的用户标识为 57741058。

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

# the ID of the user
id = 57741058

# fetching the user
user = api.get_user(id)

# fetching the name
name = user.name

print("The name of the user is : " + name)
```

**输出:**

```
The name of the user is : GeeksforGeeks

```

**示例 2:** 考虑以下配置文件:
![](img/159935125f6fbd011d182156efb24f04.png)
我们将使用屏幕名称来获取用户。上面提到的配置文件的屏幕名称是 PracticeGfG。

```
# the screen name of the user
screen_name = "PracticeGfG"

# fetching the user
user = api.get_user(screen_name)

# fetching the name
name = user.name

print("The name of the user is : " + name)
```

**输出:**

```
The name of the user is : Practice GfG

```
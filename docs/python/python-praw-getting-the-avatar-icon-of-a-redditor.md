# 蟒蛇 PRAW–获得红点师的头像图标

> 原文:[https://www . geesforgeks . org/python-praw-get-the-avatar-icon-of-a-redditor/](https://www.geeksforgeeks.org/python-praw-getting-the-avatar-icon-of-a-redditor/)

在 Reddit 中，redditor 是给用户的术语。每个 redditor 的个人资料上都有一个图标，这是他们的在线头像。我们将使用`Redditor`类的`icon_img()`属性来获取红点师头像的网址。

**例 1 :** 考虑以下 redditor :
![](img/60e5b09bcc9c0497565b34e02bcac732.png)

redditor 的用户名是:spez。

```py
# importing the module
import praw
import PIL
import urllib

# initialize with appropriate values
client_id = ""
client_secret = ""
username = ""
password = ""
user_agent = ""

# creating an authorized reddit instance
reddit = praw.Reddit(client_id = client_id, 
                     client_secret = client_secret, 
                     username = username, 
                     password = password,
                     user_agent = user_agent) 

# the name of the redditor
redditor_name = "spez"

# instantiating the Redditor class
redditor = reddit.redditor(redditor_name)

# fetching the URL of the image
url = redditor.icon_img

print("The URL of the icon image of " + redditor_name +
      " is : \n" + url)

# displaying the image
urllib.request.urlretrieve(url, "reddit.png")
img = PIL.Image.open("reddit.png")
img.show()
```

**输出:**

```py
The URL of the icon image of prez is : 
https://www.redditstatic.com/avatars/avatar_default_19_A06A42.png

```

![](img/29d3eee31c119ef3e2a332a1f903ea0f.png)

**例 2 :** 考虑以下 redditor :
![](img/c80c93faa6b2e754176bf9034d2fa3e5.png)

redditor 的用户名是:自动编码器

```py
# importing the module
import praw
import PIL
import urllib

# initialize with appropriate values
client_id = ""
client_secret = ""
username = ""
password = ""
user_agent = ""

# creating an authorized reddit instance
reddit = praw.Reddit(client_id = client_id, 
                     client_secret = client_secret, 
                     username = username, 
                     password = password,
                     user_agent = user_agent) 

# the name of the redditor
redditor_name = "AutoModerator"

# instantiating the Redditor class
redditor = reddit.redditor(redditor_name)

# fetching the URL of the image
url = redditor.icon_img

print("The URL of the icon image of " + redditor_name +
      " is : \n" + url)

# displaying the image
urllib.request.urlretrieve(url, "reddit.png")
img = PIL.Image.open("reddit.png")
img.show()
```

**输出:**

```py
The URL of the icon image of AutoModerator is : 
https://styles.redditmedia.com/t5_1yz875/styles/profileIcon_klqlly9fc4l41.png?width=256&height=256&crop=256:256, smart&s=94486fc13b9ca9e154e9e8926e3d8c43ccc80be3

```

![](img/fb8063ff85bba7fa643059cdcb944f11.png)
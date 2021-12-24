# 推特-文本-python (ttp)模块-Python

> 原文:[https://www . geesforgeks . org/Twitter-text-python-TTP-module-python/](https://www.geeksforgeeks.org/twitter-text-python-ttp-module-python/)

**`twitter-text-python`** 是 Python 的一个 Tweet 解析器和格式化器。本模块可以执行的任务包括:

*   **回复:**推文回复到的句柄的用户名。
*   **用户:**推文中提到的所有用户名。
*   **标签:**推文中提到的所有标签。
*   **网址:**推文中提到的所有网址。
*   **html :** 给上面提到的字段添加超链接。

**例 1 :**

```py
# import the twitter-text-python module
from ttp import ttp

# the text to be parsed
tweet_text = ("@twitter Sample tweet containing different components." +
             "# gfg # tweeple Visit : https://twitter.com @TwitterIndia")

# instantiating the Parser
p = ttp.Parser()

# parsing the text
result = p.parse(tweet_text)

# printing the username of the
# account being replied to
print("The username being replied to is : " + result.reply)

# printing all the usernames
# mentioned in the tweet
print("\nAll the usernames mentioned are : " + str(result.users))

# printing all the hashtags
# mentioned in the tweet
print("\nAll the hashtags mentioned are : " + str(result.tags))

# printing all the URLs
# mentioned in the tweet
print("\nAll the URLs mentioned are : " + str(result.urls))

# adding hyperlinks to usernames,
# hashtags and URLs
print(result.html)
```

**输出:**

> 回复的用户名是:twitter
> 
> 所有提到的用户名都是:['推特'，'推特印度']
> 
> 所有提到的标签都是:['gfg '，' tweeple']
> 
> 所有提到的网址都是:['https://twitter.com']
> 
> [@twitter](https://twitter.com/twitter) 包含不同成分的样本推文。[# gfg](https://twitter.com/search?q=%23gfg)# T4】# tweeple 访问:[https://twitter.com](https://twitter.com)T8】@推特印度

**例 2 :** 我们也可以通过做`include_spans = True`找到弦(POS)的位置。

```py
# import the twitter-text-python module
from ttp import ttp

# the text to be parsed
tweet_text = ("@twitter Sample tweet containing different components." +
             "# gfg # tweeple Visit : https://twitter.com @TwitterIndia")

# instantiating the Parser
# with spans
p = ttp.Parser(include_spans = True)

# parsing the text
result = p.parse(tweet_text)

# printing all the usernames
# mentioned in the tweet with POS
print("All the usernames mentioned are : " + str(result.users))

# printing all the hashtags
# mentioned in the tweet with POS
print("\nAll the hashtags mentioned are : " + str(result.tags))

# printing all the URLs
# mentioned in the tweet with POS
print("\nAll the URLs mentioned are : " + str(result.urls))
```

**输出:**

> 所有提到的用户名都是:[('twitter '，(0，8))，(' TwitterIndia '，(130，143))]
> 
> 所有提到的标签都是:[('gfg '，(96，100))，(' tweeple '，(101，109))]
> 
> 所有提到的网址是:[('https://twitter.com '，(76，95))]
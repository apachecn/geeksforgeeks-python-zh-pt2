# 使用硒 Python 的 Twitter 自动化

> 原文:[https://www . geesforgeks . org/Twitter-自动化-使用-selenium-python/](https://www.geeksforgeeks.org/twitter-automation-using-selenium-python/)

如果你和我一样认为推特比 Instagram 好得多，那么我可能有东西给你。我们都知道在推特上获得关注者是非常困难的，但是有时候转发高质量的内容也能获得关注者。显然，你是一个忙碌的人，没有时间坐在手机或笔记本电脑上阅读和转发内容。相当无聊的任务对吧？让我们聪明的朋友来做吧。本文围绕如何使用 selenium Python 自动化 twitter 展开。

首先，你将需要 **Python** 。你可以从[这里](https://www.python.org/downloads/)下载 python。现在，让我们开始编码。首先，创建一个名为**推特自动化**的文件夹，然后将目录更改为新创建的文件夹。现在，创建一个名为 *requirements.txt* 的文件，并在其中添加这一行。

```py
selenium==3.141.0
```

接下来，打开你的终端并输入

```py
pip install -r requirements.txt
```

接下来，您将需要一个 *chrome 驱动程序*。你可以从[这里](https://chromedriver.chromium.org/downloads)下载。下载完成后，将下载的驱动程序移动到您新创建的文件夹*推特自动化*。
现在所有要求都处理好了。现在让我们从编码开始。
现在，创建一个名为 *credentials.txt* 的文件，并在其中添加以下几行。

```py
email: {your twitter email}
password: {your twitter password}
```

用你的 twitter 原始凭证替换电子邮件和密码占位符。我正在使用文本文件。人们也可以使用*。env* 文件，但这里为了简单起见，我使用的是*。txt* 文件。

接下来，创建另一个名为 **secrets.py** 的文件，并向其中添加以下代码行。

## 蟒蛇 3

```py
"""
    Add your twitter handle's email and password
    in the credentials.txt file.
    This will be used to automate the login.
"""

def get_credentials() -> dict:
    # dictionary for storing credentials
    credentials = dict()
    # reading the text file
    # for credentials
    with open('credentials.txt') as f:
        # iterating over the lines
        for line in f.readlines():
            try:
                # fetching email and password
                key, value = line.split(": ")
            except ValueError:
                # raises error when email and password not supplied
                print('Add your email and password in credentials file')
                exit(0)
            # removing trailing
            # white space and new line
            credentials[key] = value.rstrip(" \n")
    # returning the dictionary containing the credentials
    return credentials
```

为了更好地理解，我在内联注释中添加了详细的代码解释。现在，让我们创建一个最重要的文件，一个具有所有魔力的文件。创建一个名为**twitertbot . py**的新文件，并在其中添加以下行。

## 蟒蛇 3

```py
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver import ActionChains
from selenium.webdriver.chrome.options import Options
'''Uncomment the below line when running in linux'''
# from pyvirtualdisplay import Display
import time, os

class Twitterbot:

    def __init__(self, email, password):

        """Constructor

        Arguments:
            email {string} -- registered twitter email
            password {string} -- password for the twitter account
        """

        self.email = email
        self.password = password
        # initializing chrome options
        chrome_options = Options()

        # adding the path to the chrome driver and
        # integrating chrome_options with the bot
        self.bot = webdriver.Chrome(
            executable_path = os.path.join(os.getcwd(), 'chromedriver'),
            options = chrome_options
        )

    def login(self):
        """
            Method for signing in the user
            with the provided email and password.
        """

        bot = self.bot
        # fetches the login page
        bot.get('https://twitter.com / login')
        # adjust the sleep time according to your internet speed
        time.sleep(3)

        email = bot.find_element_by_xpath(
            '//*[@id ="react-root"]/div / div / div[2]/main / div / div / form / div / div[1]/label / div / div[2]/div / input'
        )
        password = bot.find_element_by_xpath(
            '//*[@id ="react-root"]/div / div / div[2]/main / div / div / form / div / div[2]/label / div / div[2]/div / input'
        )

        # sends the email to the email input
        email.send_keys(self.email)
        # sends the password to the password input
        password.send_keys(self.password)
        # executes RETURN key action
        password.send_keys(Keys.RETURN)

        time.sleep(2)

    def like_retweet(self, hashtag):

        """
        This function automatically retrieves
        the tweets and then likes and retweets them

        Arguments:
            hashtag {string} -- twitter hashtag
        """

        bot = self.bot

        # fetches the latest tweets with the provided hashtag
        bot.get(
            'https://twitter.com / search?q =% 23' + \
            hashtag+'&src = typed_query&f = live'
        )

        time.sleep(3)

        # using set so that only unique links
        # are present and to avoid unnecessary repetition
        links = set()

        # obtaining the links of the tweets
        for _ in range(100):
            # executing javascript code
            # to scroll the webpage
            bot.execute_script(
                'window.scrollTo(0, document.body.scrollHeight)'
            )

            time.sleep(4)

            # using list comprehension
            # for adding all the tweets link to the set
            # this particular piece of code might
            # look very complicated but the only reason
            # I opted for list comprehension because is
            # lot faster than traditional loops
            [
                links.add(elem.get_attribute('href'))\
                for elem in bot.find_elements_by_xpath("//a[@dir ='auto']")
            ]

        # traversing through the generated links
        for link in links:
            # opens individual links
            bot.get(link)
            time.sleep(4)

            try:
                # retweet button selector
                bot.find_element_by_css_selector(
                    '.css-18t94o4[data-testid ="retweet"]'
                ).click()
                # initializes action chain
                actions = ActionChains(bot)
                # sends RETURN key to retweet without comment
                actions.send_keys(Keys.RETURN).perform()

                # like button selector
                bot.find_element_by_css_selector(
                    '.css-18t94o4[data-testid ="like"]'
                ).click()
                # adding higher sleep time to avoid
                # getting detected as bot by twitter
                time.sleep(10)
            except:
                time.sleep(2)

        # fetches the main homepage
        bot.get('https://twitter.com/')
```

现在，是时候编写我们的驱动程序脚本了。为此，创建一个名为 **main.py** 的文件，并在其中添加以下行。

## 蟒蛇 3

```py
import twitterbot as tb
import secrets, sys

# fetches the hashtag from command line argument
hashtag = sys.argv[1]
# fetches the credentials dictionary
# using get_credentials function
credentials = secrets.get_credentials()
# initialize the bot with your credentials
bot = tb.Twitterbot(credentials['email'], credentials['password'])
# logging in
bot.login()
# calling like_retweet function
bot.like_retweet(hashtag)
```

现在，我们完成了代码。让我们通过在您的终端中运行以下命令来调用我们的驱动程序脚本。

```py
python main.py {hashtag}
```

例如，您可以尝试用任何趋势标签来代替标签占位符

```py
python main.py python3
```

这将喜欢并转发 100 条带有标签 *python* 的推文。您可以在下面的视频中查看它的表现。
好了，这就对了。继续尝试，不要增加推文的数量，因为推特每天都有推文的限制。
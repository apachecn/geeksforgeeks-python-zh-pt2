# 使用 Flask

的推特情感分析 WebApp

> 原文:[https://www . geesforgeks . org/Twitter-情绪-分析-webapp-使用-flask/](https://www.geeksforgeeks.org/twitter-sentiment-analysis-webapp-using-flask/)

这是一个使用 Python 和 Flask 框架制作的网络应用程序。它有注册系统和仪表板。用户可以输入关键词，根据关键词检索推特直播文本，并分析其客户感受和情绪。这些数据可以用图表显示出来。特别是，这个项目使用流行的“Tweepy”API 挖掘数据。Tweepy 应用编程接口实时连接到推特，并从推特平台收集元数据和文本。

### 目的:

*   帮助公司研究特定产品的顾客情绪。
*   帮助系统用户快速高效地分析海量数据。
*   以-1 到 1 的等级隔离客户情绪，其中-1 代表对关键词的强烈负面情感，1 代表强烈的正面反应。
*   清晰有效地可视化收集的数据。

### 详细的项目实施视频:

<video class="wp-video-shortcode" id="video-620664-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210519203623/recording1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210519203623/recording1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210519203623/recording1.mp4)</video>

### **项目使用的工具和技术:**

**硬件:**

*   4GB RAM
*   Windows 10
*   用于部署的谷歌浏览器
*   连接到推特的互联网连接

本项目设计基于软件，因此硬件设计要求包括一台 64 位运行良好的电脑，至少有 4gb 内存。

**软件:**

*   Python——Python 是一种解释的、高级的、通用的编程语言。Python 提高了代码的可管理性和可读性，使其成为使用机器学习的顶级应用程序之一。
*   Flask web 框架(与 python 一起工作)- Flask 是一个 web 框架。这意味着 flask 为我们提供了工具、库和技术，可以让我构建一个网络应用程序和网页。Flask 是一个后端微框架，它使数据处理变得简洁明了。
*   Tweepy(Python 的推特应用编程接口)——Tweepy 是一个开源的 Python 包，它为您提供了一种非常方便的方法来使用 Python 访问推特应用编程接口。Tweepy 包括一组表示 Twitter 模型和 API 端点的类和方法，它透明地处理各种实现细节，例如数据编码和解码。
*   windows Xampp 服务器上的 Apache SqL-SqL 服务器在本地主机内部的 phpMyAdmin 上运行。该数据库用于存储、验证和检索用户的登录凭据。
*   Bootstrap-在 Bootstrap 的帮助下增强了用户界面，这有助于构建现代、直观和响应迅速的网页。
*   JQuery- JQuery 用于从 Tweepy API 来回发送和检索数据，并在网页上显示结果。
*   HTML/CSS- HTML 和 CSS 是网站前端设计的基础。

### **构建项目所需的技能:**

*   机器学习-中等
*   编程技能
*   Python-高级。
*   HTML/CSS/JQUERY/BOOTSTRAP-基本到中等。
*   SQL/数据库管理系统-基本到中等
*   调试/部署–中等
*   能够使用应用编程接口。

### **实施项目:**

按照以下步骤实施项目:

**步骤 1:** 在系统上下载并安装 Xampp 服务器。

**第二步:**启动 Apache Xampp 和 MySQL。在 MySQL 中创建一个包含 3 列(用户名、电子邮件 id 和密码)的数据库。

**第三步:**下载并安装 PyCharm。点击创建- >新项目。给你的项目命名。

**第 4 步:**在 Pycharm 中键入以下代码。有关详细的项目文件和层次结构，请参考这个 [GitHub 资源库。](https://github.com/Deeksha13561/SentimentAnalysis/blob/master)

### main.py 文件:

在这个文件中，我们首先初始化我们的项目。我们使用“conn”对象建立到我们的 SQL 数据库的连接。

我们设置了一个用户 cookie 变量，在将用户重定向到主页之前，它会检查用户是否已经登录。该脚本还处理登录/注册页面上的用户输入。

## 蟒蛇 3

```
from flask import Flask, render_template, request, redirect, session
import mysql.connector
from sentiments import second
import os

app = Flask(__name__)

# initializing the user cookie
app.secret_key = os.urandom(24)

# blueprint to call the second python file in the project.
app.register_blueprint(second)

# establishing a connection with mysql database made in xampp
try:
    conn = mysql.connector.connect(
        host="localhost", user="root", password="", database="users")
    cursor = conn.cursor()
except:
    print("An exception occured")

# call the login template when the url is http://localhost:5000/
@app.route('/')
def login():
    return render_template('login.html')

# call the register template when the url is http://localhost:5000/register
@app.route('/register')
def register():
    return render_template('register.html')

@app.route('/home')
def home():
    if 'user_id' in session:
        return render_template('home.html')
    else:
        return redirect('/')

@app.route('/login_validation', methods=['POST'])
def login_validation():
    email = request.form.get('email')
    password = request.form.get('password')

    cursor.execute(
        """SELECT * from `users` WHERE `email` LIKE '{}' AND `password` LIKE '{}'""".format(email, password))
    users = cursor.fetchall()
    # check if a user has already logged in
    if len(users) > 0:
        session['user_id'] = users[0][0]
        return redirect('/home')
    else:
        return redirect('/login')

@app.route('/add_user', methods=['POST'])
def add_user():

  # get user login data and pass the data to database
    name = request.form.get('uname')
    email = request.form.get('uemail')
    password = request.form.get('upassword')
    cursor.execute("""INSERT INTO `users` (`name`,`email`,`password`) VALUES ('{}','{}','{}')""".format(
        name, email, password))
    conn.commit()
    cursor.execute(
        """SELECT * from `users` WHERE `email` LIKE '{}'""".format(email))
    myuser = cursor.fetchall()
    session['user_id'] = myuser[0][0]
    return redirect('/home')

@app.route('/logout')
def logout():
  # close the session
    session.pop('user_id')
    return redirect('/')

if __name__ == "__main__":
    app.run(debug=True)
```

#### 情感

这是我们项目中的第二个 python 文件，在我们的“main.py”文件中注册为蓝图。

这段代码从 HTML 页面获取用户输入，该页面指定要搜索哪个关键字，以及要查看的推文数量。然后它连接到 Tweepy 应用编程接口，该接口检索推文文本。这篇文章被清理了，然后分成不同的情绪(-1 是愤怒/悲伤的情绪，1 是快乐的情绪)。

基于此，创建一个饼图并保存为图像。这个图像后来在其他网页中被调用。

## 蟒蛇 3

```
from flask import Blueprint, render_template, request
import matplotlib.pyplot as plt
import os

import tweepy
import csv
import re
from textblob import TextBlob
import matplotlib
matplotlib.use('agg')

# register this file as a blueprint
second = Blueprint("second", __name__, static_folder="static",
                   template_folder="template")

# render page when url is called
@second.route("/sentiment_analyzer")
def sentiment_analyzer():
    return render_template("sentiment_analyzer.html")

# class with main logic
class SentimentAnalysis:

    def __init__(self):
        self.tweets = []
        self.tweetText = []

    # This function first connects to the Tweepy API using API keys
    def DownloadData(self, keyword, tweets):

        # authenticating
        consumerKey = '//get from Tweepy'
        consumerSecret = '//get from Tweepy'
        accessToken = '//insert your access token here'
        accessTokenSecret = '//Tweepy AccessToken secret here'
        auth = tweepy.OAuthHandler(consumerKey, consumerSecret)
        auth.set_access_token(accessToken, accessTokenSecret)
        api = tweepy.API(auth, wait_on_rate_limit=True)

        # input for term to be searched and how many tweets to search
        # searchTerm = input("Enter Keyword/Tag to search about: ")
        # NoOfTerms = int(input("Enter how many tweets to search: "))
        tweets = int(tweets)

        # searching for tweets
        self.tweets = tweepy.Cursor(
            api.search, q=keyword, lang="en").items(tweets)

        # Open/create a file to append data to
        csvFile = open('result.csv', 'a')

        # Use csv writer
        csvWriter = csv.writer(csvFile)

        # creating some variables to store info
        polarity = 0
        positive = 0
        wpositive = 0
        spositive = 0
        negative = 0
        wnegative = 0
        snegative = 0
        neutral = 0

        # iterating through tweets fetched
        for tweet in self.tweets:

            # Append to temp so that we can store in csv later. I use encode UTF-8
            self.tweetText.append(self.cleanTweet(tweet.text).encode('utf-8'))

            # print (tweet.text.translate(non_bmp_map))    #print tweet's text
            analysis = TextBlob(tweet.text)

            # print(analysis.sentiment)  # print tweet's polarity
            # adding up polarities to find the average later
            polarity += analysis.sentiment.polarity

            # adding reaction of how people are reacting to find average later
            if (analysis.sentiment.polarity == 0):
                neutral += 1
            elif (analysis.sentiment.polarity > 0 and analysis.sentiment.polarity <= 0.3):
                wpositive += 1
            elif (analysis.sentiment.polarity > 0.3 and analysis.sentiment.polarity <= 0.6):
                positive += 1
            elif (analysis.sentiment.polarity > 0.6 and analysis.sentiment.polarity <= 1):
                spositive += 1
            elif (analysis.sentiment.polarity > -0.3 and analysis.sentiment.polarity <= 0):
                wnegative += 1
            elif (analysis.sentiment.polarity > -0.6 and analysis.sentiment.polarity <= -0.3):
                negative += 1
            elif (analysis.sentiment.polarity > -1 and analysis.sentiment.polarity <= -0.6):
                snegative += 1

        # Write to csv and close csv file
        csvWriter.writerow(self.tweetText)
        csvFile.close()

        # finding average of how people are reacting
        positive = self.percentage(positive, tweets)
        wpositive = self.percentage(wpositive, tweets)
        spositive = self.percentage(spositive, tweets)
        negative = self.percentage(negative, tweets)
        wnegative = self.percentage(wnegative, tweets)
        snegative = self.percentage(snegative, tweets)
        neutral = self.percentage(neutral, tweets)

        # finding average reaction
        polarity = polarity / tweets

        # printing out data
        #  print("How people are reacting on " + keyword + " by analyzing " + str(tweets) + " tweets.")
        #  print()
        #  print("General Report: ")

        if (polarity == 0):
            htmlpolarity = "Neutral"

        # print("Neutral")
        elif (polarity > 0 and polarity <= 0.3):
            htmlpolarity = "Weakly Positive"
            # print("Weakly Positive")
        elif (polarity > 0.3 and polarity <= 0.6):
            htmlpolarity = "Positive"
        elif (polarity > 0.6 and polarity <= 1):
            htmlpolarity = "Strongly Positive"
        elif (polarity > -0.3 and polarity <= 0):
            htmlpolarity = "Weakly Negative"
        elif (polarity > -0.6 and polarity <= -0.3):
            htmlpolarity = "Negative"
        elif (polarity > -1 and polarity <= -0.6):
            htmlpolarity = "strongly Negative"

        self.plotPieChart(positive, wpositive, spositive, negative,
                          wnegative, snegative, neutral, keyword, tweets)
        print(polarity, htmlpolarity)
        return polarity, htmlpolarity, positive, wpositive, spositive, negative, wnegative, snegative, neutral, keyword, tweets

    def cleanTweet(self, tweet):
        # Remove Links, Special Characters etc from tweet
        return ' '.join(re.sub("(@[A-Za-z0-9]+)|([^0-9A-Za-z \t]) | (\w +:\ / \ / \S +)", " ", tweet).split())

    # function to calculate percentage
    def percentage(self, part, whole):
        temp = 100 * float(part) / float(whole)
        return format(temp, '.2f')

    # function which sets and plots the pie chart. The chart is saved in an img file every time the project is run.
    # The previous image is overwritten. This image is called in the html page.

    def plotPieChart(self, positive, wpositive, spositive, negative, wnegative, snegative, neutral, keyword, tweets):
        fig = plt.figure()
        labels = ['Positive [' + str(positive) + '%]', 'Weakly Positive [' + str(wpositive) + '%]',
                  'Strongly Positive [' + str(spositive) +
                  '%]', 'Neutral [' + str(neutral) + '%]',
                  'Negative [' + str(negative) +
                  '%]', 'Weakly Negative [' + str(wnegative) + '%]',
                  'Strongly Negative [' + str(snegative) + '%]']
        sizes = [positive, wpositive, spositive,
                 neutral, negative, wnegative, snegative]
        colors = ['yellowgreen', 'lightgreen', 'darkgreen',
                  'gold', 'red', 'lightsalmon', 'darkred']
        patches, texts = plt.pie(sizes, colors=colors, startangle=90)
        plt.legend(patches, labels, loc="best")
        plt.axis('equal')
        plt.tight_layout()
        strFile = r"C:\Users\LENOVO\PycharmProjects\SentimentAnalysis\static\images\plot1.png"
        if os.path.isfile(strFile):
            os.remove(strFile)  # Opt.: os.system("rm "+strFile)
        plt.savefig(strFile)
        plt.show()

@second.route('/sentiment_logic', methods=['POST', 'GET'])
def sentiment_logic():

  # get user input of keyword to search and number of tweets from html form.
    keyword = request.form.get('keyword')
    tweets = request.form.get('tweets')
    sa = SentimentAnalysis()

    # set variables which can be used in the jinja supported html page
    polarity, htmlpolarity, positive, wpositive, spositive, negative, wnegative, snegative, neutral, keyword1, tweet1 = sa.DownloadData(
        keyword, tweets)
    return render_template('sentiment_analyzer.html', polarity=polarity, htmlpolarity=htmlpolarity, positive=positive, wpositive=wpositive, spositive=spositive,
                           negative=negative, wnegative=wnegative, snegative=snegative, neutral=neutral, keyword=keyword1, tweets=tweet1)

@second.route('/visualize')
def visualize():
    return render_template('PieChart.html')
```

#### SentimentAnalyzer.py 模板。(为程序的主要逻辑呈现结果的模板)

该模板要求用户输入他们感兴趣的主题/单词，以及基于该主题的用户想要分析的推文数量。

请注意，推特有每日和每小时的费率限制，不能超过。

该表单将数据传递给 second.py 文件，该文件计算输出并设置“jinja”变量。(Jinja 允许在 python 和 HTML 之间传递值)。

这些变量然后向用户显示输出。

## 超文本标记语言

```
<!DOCTYPE html>
<html lang="en">
   <head>
      <!-- Required meta tags -->
      <meta charset="utf-8">
      <meta name="viewport" content="width=device-width, initial-scale=1">
      <link rel="stylesheet" type="text/css" href="{{ url_for('static', filename='css/style.css') }}">
      <!-- Bootstrap CSS -->
      <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-eOJMYsd53ii+scO/bJGFsiCZc+5NDVN2yr8+0RDqr0Ql0h+rP48ckxlpbzKgwra6" crossorigin="anonymous">
      <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
      <script src="https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css"></script>
      <title>Home</title>
   </head>
   <body class="bg-nav">
      <!-- code for the navigation header bar-->
      <header style="height: 80px" class="navbar navbar-dark sticky-top bg-nav flex-md-nowrap p-0 shadow">
         <a class="navbar-brand col-md-3 col-lg-2 me-0 px-3" style="font-size: 30px; font-weight: bold" href="#">Twitter Sentiment Analysis</a>
         <button class="navbar-toggler position-absolute d-md-none collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#sidebarMenu" aria-controls="sidebarMenu" aria-expanded="false" aria-label="Toggle navigation">
         <span class="navbar-toggler-icon"></span>
         </button>
         <nav class="d-inline-flex mt-2 mt-md-0 ms-md-auto">
            <a class="me-3 py-2 text-decoration-none text-light" style="font-size: 20px" href="/sentiment_analyzer">Get started</a>
            <a class="me-3 py-2 text-light text-decoration-none" style="font-size: 20px" href="/home">Home</a>
            <a class="me-3 py-2 text-light text-decoration-none" style="font-size: 20px"  href="/visualize">Visualize</a>
            <a class="py-2 text-light text-decoration-none" style="font-size: 20px" href="https://www.tweepy.org/">Help</a>
         </nav>
         <ul class="navbar-nav px-3">
            <li class="nav-item text-nowrap">
               <a class="nav-link text-dark card" style="font-size: 20px; padding: 3px" href="/logout">Sign out</a>
            </li>
         </ul>
      </header>
      <div class="container">
         <div class="row">
            <div class="card mt-100" style="margin-top: 50px">
               <div class="card-body">
                  <form method="post" action="sentiment_logic">
                     <label> Enter your search keyword </label><br>
                     <input type="text" class="form-control" name="keyword"> <br>
                     <label> Enter your number of tweets to analyze </label><br>
                     <input type="number" class="form-control" name="tweets"><br>
                     <input type="submit" class="btn btn-primary btn-block btn-lg" value="Search">
                  </form>
                  <br>

<p> Need help? <a href="/register"> Click here </a></p>

               </div>
            </div>
         </div>
      </div>
      <!-- Optional JavaScript; choose one of the two! -->
      <!--output values-->
      <br>
      <br>
      <br>
      <h1 style="color: black">-----------------------------------------------------------------------------------</h1>
      <div style="text-align: center;">
         <div >
            {% if polarity %}
            <h3 style="color: white; text-align: center;font-size:30px; border-radius: 25px; background-color: black">How are people reacting on {{keyword}} by analyzing {{tweets}} Tweets</h3>
            {% endif %}
         </div>
      </div>
      <!--parent div for reports-->
      <div class="row">
         <div>
            <!--General sentiment report-->
            <div class="row">
               <div class="mt-100">
                  <h1 style="color: white; text-align: center;font-size:50px">General Report</h1>
                  <div class="alert alert-primary" role="alert" style="height:70px">
                     {% if polarity %}
                     <h1 style="text-align: center;font-size:30px"> The Average Sentiment is {{htmlpolarity}}  </h1>
                     {%endif%}
                  </div>
               </div>
            </div>
            <!--end of general report-->
            <!--start of polarity value-->
            <div class="row">
               <div class="mt-100">
                  <h1 style="color: white; text-align: center;font-size:50px">Sentiment Polarity</h1>
                  <div class="alert alert-primary" role="alert" style="height:70px">
                     {% if polarity %}
                     <h1 style="text-align: center;font-size:30px"> The sentiment polarity is {{polarity}} </h1>
                     {%endif%}
                  </div>
               </div>
            </div>
            <!--end of polarity value-->
         </div>
         <!-- end of parent div for reports-->
      </div>
      <div style="margin-top: 50px">
         <h1 style="color: white; text-align: center;font-size:50px">Detailed Report</h1>
         <div class="alert alert-primary" role="alert" style="height:400px">
            {% if polarity %}
            <h2 class="report-text"> {{spositive}} "% people thought it was strongly positive"</h2>
            <h2 class="report-text"> {{positive}} "% people thought it was positive"</h2>
            <h2 class="report-text"> {{wpositive}} "% people thought it was weakly positive"</h2>
            <h2 class="report-text"> {{neutral}} "% people thought it was neutral"</h2>
            <h2 class="report-text"> {{negative}} "% people thought it was negative"</h2>
            <h2 class="report-text"> {{wnegative}} "% people thought it was weakly negative"</h2>
            <h2 class="report-text"> {{snegative}} "% people thought it was strongly negative"</h2>
            {%endif%}
         </div>
      </div>
      <!--end of report-->
      <a href="visualize" class="btn btn-primary btn-block btn-lg" style="background-color: crimson; font-size: 30px"> Generate Visualization</a>
      <br>
      <br>
      <!-- Option 1: Bootstrap Bundle with Popper -->
      <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta3/dist/js/bootstrap.bundle.min.js" integrity="sha384-JEW9xMcG8R+pH31jmWH6WWP0WintQrMb4s7ZOdauHnUtxwoG2vI5DkLtS3qm9Ekf" crossorigin="anonymous"></script>
      <!-- Option 2: Separate Popper and Bootstrap JS -->
      <!--
         <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.1/dist/umd/popper.min.js" integrity="sha384-SR1sx49pcuLnqZUnnPwx6FCym0wLsk5JZuNx2bPPENzswTNFaQU1RDvt3wT4gWFG" crossorigin="anonymous"></script>
         <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta3/dist/js/bootstrap.min.js" integrity="sha384-j0CNLUeiqtyaRmlzUHCPZ+Gy5fQu0dQ6eZ/xAww941Ai1SxSY+0EQqNXNE6DZiVc" crossorigin="anonymous"></script>
         -->
   </body>
</html>
```
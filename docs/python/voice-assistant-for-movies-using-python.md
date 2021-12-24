# 使用 Python 的电影语音助手

> 原文:[https://www . geesforgeks . org/voice-assistant-for-movies-use-python/](https://www.geeksforgeeks.org/voice-assistant-for-movies-using-python/)

在这篇文章中，我们将看到如何制作一个语音助手来搜索电影。在以音频格式输入电影名称后，它也会以音频格式提供该电影的信息。

众所周知，最大的电影搜索网站是 IMDb。IMDb 是一个与电影、电视节目、家庭视频、视频游戏和在线流媒体内容相关的在线信息数据库，包括演员、制作团队、个人传记、情节摘要、琐事、收视率、粉丝和评论。

### **要求:**

*   **IMDbPY:** 这是一个 Python 包，用于检索和管理 IMDb 电影数据库中关于电影、人物、角色和公司的数据。可以使用以下命令安装:

```
pip install IMDbPY
```

*   **pyttsx3:** 是 Python 中的文本到语音转换库。与替代库不同，它脱机工作，并且兼容 Python 2 和 3。可以使用以下命令安装:

```
pip install pyttsx3
```

*   **语音识别:**用于执行语音识别的库，支持多种引擎和 API，在线和离线。可以使用以下命令安装:

```
pip install SpeechRecognition
```

*   **日期时间:**日期/时间值的封装。可以使用以下命令安装:

```
pip install DateTime
```

### 方法:

*   导入所需模块。
*   创建以下功能:
    *   **speak( ):** 这个功能会帮助我们的助手说出来。
    *   **get_audio( ):** 该功能将帮助助手获取用户的输入。
    *   **get_movies( ):** 该功能将帮助助手搜索作为输入给出的电影。
*   创建一个新的函数 **search_movie( )** 使用上面的函数调用来搜索电影。
*   调用上面创建的函数。

下面是实现。

## 蟒蛇 3

```
# importing all required libraries
import imdb
import pyttsx3
import speech_recognition as sr
import datetime

# Function for speaking
def speak(text):
    engine = pyttsx3.init()
    voices = engine.getProperty('voices')
    engine.setProperty('voice', voices[1].id)
    rate = engine.getProperty('rate')

    engine.setProperty('rate', rate-20)

    engine.say(text)
    engine.runAndWait()

# calling the speak() function
speak("Say the movie name")

# Function to get input in the audio format
def get_audio():
    r = sr.Recognizer()
    with sr.Microphone() as source:
        r.pause_threshold = 1
        r.adjust_for_ambient_noise(source, duration=1)
        audio = r.listen(source)
        said = ""

    try:

        # will recognize the input
        said = r.recognize_google(audio)
        print(said)

    except:
        speak("Didn't get that")
    # will return the input in lowercase
    return said.lower()

# Function for searching movie
def search_movie():

    # gathering information from IMDb
    moviesdb = imdb.IMDb()

    # search for title
    text = get_audio()

    # passing input for searching movie
    movies = moviesdb.search_movie(text)

    speak("Searching for " + text)
    if len(movies) == 0:
        speak("No result found")
    else:

        speak("I found these:")

        for movie in movies:

            title = movie['title']
            year = movie['year']
            # speaking title with releasing year
            speak(f'{title}-{year}')

            info = movie.getID()
            movie = moviesdb.get_movie(info)

            title = movie['title']
            year = movie['year']
            rating = movie['rating']
            plot = movie['plot outline']

            # the below if-else is for past and future release
            if year < int(datetime.datetime.now().strftime("%Y")):
                speak(
                    f'{title}was released in {year} has IMDB rating of {rating}.\
                    The plot summary of movie is{plot}')
                print(
                    f'{title}was released in {year} has IMDB rating of {rating}.\
                    The plot summary of movie is{plot}')
                break

            else:
                speak(
                    f'{title}will release in {year} has IMDB rating of {rating}.\
                    The plot summary of movie is{plot}')
                print(
                    f'{title}will release in {year} has IMDB rating of {rating}.\
                    The plot summary of movie is{plot}')
                break

search_movie()
```

当用户输入时，上面的代码将说出电影的信息，并打印出来。

**输出:**

<video class="wp-video-shortcode" id="video-555677-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210209133031/My-Video1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210209133031/My-Video1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210209133031/My-Video1.mp4)</video>

> 寄生虫
> 
> Parasitewas 于 2019 年发布，IMDB 评级为 8.6。
> 
> 电影的情节总结是金家——父母钟淑和基泽，以及他们年轻的成年后代，儿子基佑和女儿基贞——是一个贫穷的家庭，住在首尔一个繁忙的下层工人阶级商业区一个破旧狭窄的半地下室公寓里。
> 
> 他们甚至不知道，尤其是金先生和金太太，真的闻到了贫穷的味道。通常作为一个集体，他们犯下一些小骗局来维持生活，即使他们有工作，他们也只做最起码的工作。基宇就是那个梦想着有一天能上大学摆脱贫困的人。
> 
> 尽管没有接受过大学教育，但他的大学同学朋友闵选择将他的辅导工作交给朴大惠，闵计划在他回到首尔后和朴大惠约会，而她自己也在上大学。
> 
> 帕克一家是一个富裕的家庭，四年来他们一直住在由著名建筑师南国设计的现代主义风格的房子里。朴先生和朴夫人都是为了地位，而朴夫人却有着轻浮、头脑简单的心态和气质，
> 
> 闵告诉基宇，为了得到这份工作，他可以坦然地向她隐瞒自己的学历。在得到这份工作的过程中，基宇进一步了解到朴槿惠正在为她青春期的儿子大松寻找艺术治疗师，基宇很快推荐了他的专业艺术治疗师朋友“杰西卡”，
> 
> 真的，他认识的 Ki-jung 可以在成为四个 Kim 中最容易说谎的人时完成骗局。在基宇也爱上了大惠的时候，他开始想象自己在那所房子里，因此金家作为一个集体开始了一个计划，让所有金家，像使用化名的基荣一样，代替公园雇佣的现有仆人来策划他们被解雇的原因。
> 
> 最难摆脱的可能是文光，公园的女管家，她确实是和房子一起来的——她是南国住在那里时的女管家——因此比公园本身更了解所有的小角落和缝隙。问题就变成了金家在寻求成为他们的公园版本的过程中，能在多大程度上利用这个骗局。
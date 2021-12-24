# 使用 python 的语音助手

> 原文:[https://www.geeksforgeeks.org/voice-assistant-using-python/](https://www.geeksforgeeks.org/voice-assistant-using-python/)

众所周知，Python 是一种适合编剧和开发人员的语言。让我们使用 Python 为语音助手编写一个脚本。助手的查询可以根据用户的需要进行操作。
语音识别是将音频转换为文本的过程。这通常用于语音助手，如 Alexa、Siri 等。Python 提供了一个名为**语音识别**的应用编程接口，允许我们将音频转换成文本进行进一步处理。在本文中，我们将研究使用 python 中的 SpeechRecognition API 将大型或长音频文件转换为文本。

#### 需要的模块

*   **子流程:-** 此模块用于获取系统子流程的详细信息，这些信息用于各种命令，如关机、睡眠等。这个模块内置了 Python。

*   WolframAlpha **:-** 它用于使用 Wolfram 的算法、知识库和 AI 技术计算专家级别的答案。要安装此模块，请在终端中键入以下命令。

```
pip install wolframaplha
```

*   **Pyttsx3:-** 该模块用于在脱机工作的程序中将文本转换为语音。要安装此模块，请在终端中键入以下命令。
    T3】pip 安装 pyttsx3T5】
*   **Tkinter:-** 该模块用于构建 GUI，内置 Python。这个模块内置了 Python。

*   **维基百科:-** 众所周知，维基百科是一个伟大的知识来源，就像 GeeksforGeeks 一样，我们使用维基百科模块从维基百科获取信息或执行维基百科搜索。要安装此模块，请在终端中键入以下命令。

```
pip install wikipedia
```

*   **语音识别:-** 由于我们正在构建一个语音助手的应用程序，其中最重要的一点是您的助手能够识别您的语音(表示您想要说/问的内容)。要安装此模块，请在终端中键入以下命令。

```
pip install SpeechRecognition
```

*   **网页浏览器:-** 执行网页搜索。这个模块内置了 Python。

*   **捕捉:-** 从相机中捕捉图像。要安装此模块，请在终端中键入以下命令。

```
pip install ecapture
```

*   **py challels:-**py challels 用于收集互联网上的 Python 笑话。要安装此模块，请在终端中键入以下命令。
    **皮普安装皮笑话**

*   **日期时间:-** 日期和时间用于显示日期和时间。这个模块内置了 Python。

*   **Twilio:-** Twilio 用于打电话和发消息。要安装此模块，请在终端中键入以下命令。

```
pip install twilio
```

*   **请求:** Requests 用于发出 GET 和 POST 请求。要安装此模块，请在终端中键入以下命令。
    **pip 安装请求**

*   **美人计:**美人计是一个库，可以方便的从网页上刮取信息。要安装此模块，请在终端中键入以下命令。

```
pip install beautifulsoup4
```

**注意:**如果你不想使用这个功能，你可以删除一些导入文件，如这里的 twilio，如果你不想使用这个功能，你可以简单地删除这个功能。

#### 实现
导入以下库。

## 蟒蛇 3

```
import subprocess
import wolframalpha
import pyttsx3
import tkinter
import json
import random
import operator
import speech_recognition as sr
import datetime
import wikipedia
import webbrowser
import os
import winshell
import pyjokes
import feedparser
import smtplib
import ctypes
import time
import requests
import shutil
from twilio.rest import Client
from client.textui import progress
from ecapture import ecapture as ec
from bs4 import BeautifulSoup
import win32com.client as wincl
from urllib.request import urlopen
```

现在我们将我们的引擎设置为 Pyttsx3，它在 Python 中用于文本到语音，sapi5 是微软语音应用平台接口，我们将使用它来实现文本到语音功能。

## 蟒蛇 3

```
engine = pyttsx3.init('sapi5')
voices = engine.getProperty('voices')
engine.setProperty('voice', voices[1].id)
```

您可以在使用助手时将男性语音的语音标识更改为“0”，这里我们使用女性语音进行所有文本到语音的转换

## 蟒蛇 3

```
def speak(audio):
    engine.say(audio)
    engine.runAndWait()

def wishMe():
    hour = int(datetime.datetime.now().hour)
    if hour>= 0 and hour<12:
        speak("Good Morning Sir !")

    elif hour>= 12 and hour<18:
        speak("Good Afternoon Sir !")  

    else:
        speak("Good Evening Sir !") 

    assname =("Jarvis 1 point o")
    speak("I am your Assistant")
    speak(assname)

def username():
    speak("What should i call you sir")
    uname = takeCommand()
    speak("Welcome Mister")
    speak(uname)
    columns = shutil.get_terminal_size().columns

    print("#####################".center(columns))
    print("Welcome Mr.", uname.center(columns))
    print("#####################".center(columns))

    speak("How can i Help you, Sir")

def takeCommand():

    r = sr.Recognizer()

    with sr.Microphone() as source:

        print("Listening...")
        r.pause_threshold = 1
        audio = r.listen(source)

    try:
        print("Recognizing...")   
        query = r.recognize_google(audio, language ='en-in')
        print(f"User said: {query}\n")

    except Exception as e:
        print(e)   
        print("Unable to Recognize your voice.") 
        return "None"

    return query

def sendEmail(to, content):
    server = smtplib.SMTP('smtp.gmail.com', 587)
    server.ehlo()
    server.starttls()

    # Enable low security in gmail
    server.login('your email id', 'your email password')
    server.sendmail('your email id', to, content)
    server.close()
```

**Main Function 从这里开始，我们现在将在 Main Function 中调用所有这些函数。**

## 蟒蛇 3

```
if __name__ == '__main__':
    clear = lambda: os.system('cls')

    # This Function will clean any
    # command before execution of this python file
    clear()
    wishMe()
    username()

    while True:

        query = takeCommand().lower()

        # All the commands said by user will be
        # stored here in 'query' and will be
        # converted to lower case for easily
        # recognition of command
        if 'wikipedia' in query:
            speak('Searching Wikipedia...')
            query = query.replace("wikipedia", "")
            results = wikipedia.summary(query, sentences = 3)
            speak("According to Wikipedia")
            print(results)
            speak(results)

        elif 'open youtube' in query:
            speak("Here you go to Youtube\n")
            webbrowser.open("youtube.com")

        elif 'open google' in query:
            speak("Here you go to Google\n")
            webbrowser.open("google.com")

        elif 'open stackoverflow' in query:
            speak("Here you go to Stack Over flow.Happy coding")
            webbrowser.open("stackoverflow.com")  

        elif 'play music' in query or "play song" in query:
            speak("Here you go with music")
            # music_dir = "G:\\Song"
            music_dir = "C:\\Users\\GAURAV\\Music"
            songs = os.listdir(music_dir)
            print(songs)   
            random = os.startfile(os.path.join(music_dir, songs[1]))

        elif 'the time' in query:
            strTime = datetime.datetime.now().strftime("% H:% M:% S")   
            speak(f"Sir, the time is {strTime}")

        elif 'open opera' in query:
            codePath = r"C:\\Users\\GAURAV\\AppData\\Local\\Programs\\Opera\\launcher.exe"
            os.startfile(codePath)

        elif 'email to gaurav' in query:
            try:
                speak("What should I say?")
                content = takeCommand()
                to = "Receiver email address"   
                sendEmail(to, content)
                speak("Email has been sent !")
            except Exception as e:
                print(e)
                speak("I am not able to send this email")

        elif 'send a mail' in query:
            try:
                speak("What should I say?")
                content = takeCommand()
                speak("whome should i send")
                to = input()   
                sendEmail(to, content)
                speak("Email has been sent !")
            except Exception as e:
                print(e)
                speak("I am not able to send this email")

        elif 'how are you' in query:
            speak("I am fine, Thank you")
            speak("How are you, Sir")

        elif 'fine' in query or "good" in query:
            speak("It's good to know that your fine")

        elif "change my name to" in query:
            query = query.replace("change my name to", "")
            assname = query

        elif "change name" in query:
            speak("What would you like to call me, Sir ")
            assname = takeCommand()
            speak("Thanks for naming me")

        elif "what's your name" in query or "What is your name" in query:
            speak("My friends call me")
            speak(assname)
            print("My friends call me", assname)

        elif 'exit' in query:
            speak("Thanks for giving me your time")
            exit()

        elif "who made you" in query or "who created you" in query:
            speak("I have been created by Gaurav.")

        elif 'joke' in query:
            speak(pyjokes.get_joke())

        elif "calculate" in query:

            app_id = "Wolframalpha api id"
            client = wolframalpha.Client(app_id)
            indx = query.lower().split().index('calculate')
            query = query.split()[indx + 1:]
            res = client.query(' '.join(query))
            answer = next(res.results).text
            print("The answer is " + answer)
            speak("The answer is " + answer)

        elif 'search' in query or 'play' in query:

            query = query.replace("search", "")
            query = query.replace("play", "")         
            webbrowser.open(query)

        elif "who i am" in query:
            speak("If you talk then definitely your human.")

        elif "why you came to world" in query:
            speak("Thanks to Gaurav. further It's a secret")

        elif 'power point presentation' in query:
            speak("opening Power Point presentation")
            power = r"C:\\Users\\GAURAV\\Desktop\\Minor Project\\Presentation\\Voice Assistant.pptx"
            os.startfile(power)

        elif 'is love' in query:
            speak("It is 7th sense that destroy all other senses")

        elif "who are you" in query:
            speak("I am your virtual assistant created by Gaurav")

        elif 'reason for you' in query:
            speak("I was created as a Minor project by Mister Gaurav ")

        elif 'change background' in query:
            ctypes.windll.user32.SystemParametersInfoW(20,
                                                       0,
                                                       "Location of wallpaper",
                                                       0)
            speak("Background changed successfully")

        elif 'open bluestack' in query:
            appli = r"C:\\ProgramData\\BlueStacks\\Client\\Bluestacks.exe"
            os.startfile(appli)

        elif 'news' in query:

            try:
                jsonObj = urlopen('''https://newsapi.org / v1 / articles?source = the-times-of-india&sortBy = top&apiKey =\\times of India Api key\\''')
                data = json.load(jsonObj)
                i = 1

                speak('here are some top news from the times of india')
                print('''=============== TIMES OF INDIA ============'''+ '\n')

                for item in data['articles']:

                    print(str(i) + '. ' + item['title'] + '\n')
                    print(item['description'] + '\n')
                    speak(str(i) + '. ' + item['title'] + '\n')
                    i += 1
            except Exception as e:

                print(str(e))

        elif 'lock window' in query:
                speak("locking the device")
                ctypes.windll.user32.LockWorkStation()

        elif 'shutdown system' in query:
                speak("Hold On a Sec ! Your system is on its way to shut down")
                subprocess.call('shutdown / p /f')

        elif 'empty recycle bin' in query:
            winshell.recycle_bin().empty(confirm = False, show_progress = False, sound = True)
            speak("Recycle Bin Recycled")

        elif "don't listen" in query or "stop listening" in query:
            speak("for how much time you want to stop jarvis from listening commands")
            a = int(takeCommand())
            time.sleep(a)
            print(a)

        elif "where is" in query:
            query = query.replace("where is", "")
            location = query
            speak("User asked to Locate")
            speak(location)
            webbrowser.open("https://www.google.nl / maps / place/" + location + "")

        elif "camera" in query or "take a photo" in query:
            ec.capture(0, "Jarvis Camera ", "img.jpg")

        elif "restart" in query:
            subprocess.call(["shutdown", "/r"])

        elif "hibernate" in query or "sleep" in query:
            speak("Hibernating")
            subprocess.call("shutdown / h")

        elif "log off" in query or "sign out" in query:
            speak("Make sure all the application are closed before sign-out")
            time.sleep(5)
            subprocess.call(["shutdown", "/l"])

        elif "write a note" in query:
            speak("What should i write, sir")
            note = takeCommand()
            file = open('jarvis.txt', 'w')
            speak("Sir, Should i include date and time")
            snfm = takeCommand()
            if 'yes' in snfm or 'sure' in snfm:
                strTime = datetime.datetime.now().strftime("% H:% M:% S")
                file.write(strTime)
                file.write(" :- ")
                file.write(note)
            else:
                file.write(note)

        elif "show note" in query:
            speak("Showing Notes")
            file = open("jarvis.txt", "r")
            print(file.read())
            speak(file.read(6))

        elif "update assistant" in query:
            speak("After downloading file please replace this file with the downloaded one")
            url = '# url after uploading file'
            r = requests.get(url, stream = True)

            with open("Voice.py", "wb") as Pypdf:

                total_length = int(r.headers.get('content-length'))

                for ch in progress.bar(r.iter_content(chunk_size = 2391975),
                                       expected_size =(total_length / 1024) + 1):
                    if ch:
                      Pypdf.write(ch)

        # NPPR9-FWDCX-D2C8J-H872K-2YT43
        elif "jarvis" in query:

            wishMe()
            speak("Jarvis 1 point o in your service Mister")
            speak(assname)

        elif "weather" in query:

            # Google Open weather website
            # to get API of Open weather
            api_key = "Api key"
            base_url = "http://api.openweathermap.org / data / 2.5 / weather?"
            speak(" City name ")
            print("City name : ")
            city_name = takeCommand()
            complete_url = base_url + "appid =" + api_key + "&q =" + city_name
            response = requests.get(complete_url)
            x = response.json()

            if x["cod"] != "404":
                y = x["main"]
                current_temperature = y["temp"]
                current_pressure = y["pressure"]
                current_humidiy = y["humidity"]
                z = x["weather"]
                weather_description = z[0]["description"]
                print(" Temperature (in kelvin unit) = " +str(current_temperature)+"\n atmospheric pressure (in hPa unit) ="+str(current_pressure) +"\n humidity (in percentage) = " +str(current_humidiy) +"\n description = " +str(weather_description))

            else:
                speak(" City Not Found ")

        elif "send message " in query:
                # You need to create an account on Twilio to use this service
                account_sid = 'Account Sid key'
                auth_token = 'Auth token'
                client = Client(account_sid, auth_token)

                message = client.messages \
                                .create(
                                    body = takeCommand(),
                                    from_='Sender No',
                                    to ='Receiver No'
                                )

                print(message.sid)

        elif "wikipedia" in query:
            webbrowser.open("wikipedia.com")

        elif "Good Morning" in query:
            speak("A warm" +query)
            speak("How are you Mister")
            speak(assname)

        # most asked question from google Assistant
        elif "will you be my gf" in query or "will you be my bf" in query:  
            speak("I'm not sure about, may be you should give me some time")

        elif "how are you" in query:
            speak("I'm fine, glad you me that")

        elif "i love you" in query:
            speak("It's hard to understand")

        elif "what is" in query or "who is" in query:

            # Use the same API key
            # that we have generated earlier
            client = wolframalpha.Client("API_ID")
            res = client.query(query)

            try:
                print (next(res.results).text)
                speak (next(res.results).text)
            except StopIteration:
                print ("No results")

        # elif "" in query:
            # Command go here
            # For adding more commands
```

**输出:**

> 听…
> 认…
> 用户说:高拉夫
> # # # # # # # # # # # # T3】欢迎高拉夫先生
> # # # # # # # # # # T5】听…
> 认…
> 用户说:是的
> (‘作为今天在座的历史专业的各位太了解了，当当权者发明自己的事实并攻击质疑他们的人时，这可能标志着自由社会结束的开始。这不是夸张。这是历史上独裁政权的所作所为。他们试图控制现实。不仅是我们的法律、权利和预算，还有我们的思想和信仰。、‘希拉里·克林顿’
> 倾听……
> 识别……
> 用户称:维基百科
> 中的 Gaurav Gaurav 是印度和尼泊尔的男性名字。这个名字字面意思是骄傲。
> ==名为 Gaurav 的知名人士==
> Gaurav S Bajaj，印度电视演员
> Gaurav Bhatt，印度音乐总监、歌手、词曲作者。
> 听…
> 识别…
> 用户说:打开 YouTube
> 听…
> 识别…
> 无法识别你的声音。
> 听…
> 识别…
> 用户说:退出
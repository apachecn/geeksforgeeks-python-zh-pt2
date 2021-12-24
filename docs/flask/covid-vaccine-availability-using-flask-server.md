# 使用烧瓶服务器获得 Covid 疫苗

> 原文:[https://www . geesforgeks . org/co vid-疫苗-可用性-使用-烧瓶-服务器/](https://www.geeksforgeeks.org/covid-vaccine-availability-using-flask-server/)

在本文中，我们将使用 Flask Server 构建 **Covid 疫苗可用性检查器。**

我们都知道，整个世界都在遭受疫情病毒的折磨，唯一能帮助我们摆脱这种局面的就是大规模疫苗接种。但正如我们所知，由于该国人口众多，在我们附近地区很难找到疫苗。因此，现在技术进入了我们的视野，我们将建立自己的 covid 疫苗可用性检查器，它可以发现我们附近地区的疫苗可用性。

我们将使用一些 python 库来查找疫苗的可用性，并使用烧瓶服务器显示它们。将来，您也可以将其部署在实时服务器上。首先，我们必须使用下面的命令安装 python Flask 包:

```
pip install flask
```

安装 python 烧瓶包后，打开 Pycharm 或任何 IDE(最好是 Visual Studio 代码)并创建一个新项目。之后制作一个主 python 文件 **app.py** 和两个名为**模板**的文件夹，另一个是**静态**(文件夹名称必须和写的一样)。

下面是代表项目目录结构的图片。

![](img/480e9fbdec418bfa7c17a5e1a6142dbf.png)

## **分步实施**

**步骤 1:** 在第一步中，我们必须导入 python 库，我们将在项目中进一步使用这些库。另外，制作一个 Flask 服务器的应用程序。

## 计算机编程语言

```
from flask import Flask,request,session,render_template
import requests,time
from datetime import datetime,timedelta

app = Flask(__name__)
```

**步骤 2:** 添加路由来处理客户端请求。

## 蟒蛇 3

```
@app.route('/')
def home():

    # rendering the homepage of project
    return render_template("index.html")

@app.route('/CheckSlot')
def check():

    # for checking the slot available or not

    # fetching pin codes from flask
    pin = request.args.get("pincode")

    # fetching age from flask
    age = request.args.get("age")
    data = list()

    # finding the slot
    result = findSlot(age, pin, data)

    if(result == 0):
        return render_template("noavailable.html")
    return render_template("slot.html", data=data)
```

**第三步:**这是我们项目的主要步骤，找到疫苗的可用性(findslot()函数，将做以下事情):

*   首先从 python 的 DateTime 库中获取年龄、pin 和查找日期等参数。
*   从 cowin 官方网站上删除数据，如疫苗剂量、疫苗接种中心、可用性、疫苗类型和价格等。
*   将所有数据存储在 python 列表中。

## 蟒蛇 3

```
def findSlot(age,pin,data):

    flag = 'y'
    num_days =  2
    actual = datetime.today()
    list_format = [actual + timedelta(days=i) for i in range(num_days)]
    actual_dates = [i.strftime("%d-%m-%Y") for i in list_format]

    while True:
        counter = 0
        for given_date in actual_dates:

            # cowin website Api for fetching the data
            URL = "https://cdn-api.co-vin.in/api/v2/appointment/sessions/public/calendarByPin?pincode={}&date={}".format(pin, given_date)
            header = {'User-Agent': 'Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.76 Safari/537.36'}

            # Get the results in json format.
            result = requests.get(URL,headers = header)
            if(result.ok):
                response_json = result.json()
                if(response_json["centers"]):

                    # Checking if centres available or not
                    if(flag.lower() == 'y'):
                        for center in response_json["centers"]:

                            # For Storing all the centre and all parameters
                            for session in center["sessions"]:

                                # Fetching the availability in particular session
                                datas = list()

                                # Adding the pincode of area in list
                                datas.append(pin)

                                # Adding the dates available in list
                                datas.append(given_date)

                                # Adding the centre name in list
                                datas.append(center["name"])

                                # Adding the block name in list
                                datas.append(center["block_name"])

                                # Adding the vaccine cost type whether it is
                                # free or chargable.
                                datas.append(center["fee_type"])

                                # Adding the available capacity or amount of 
                                # doses in list
                                datas.append(session["available_capacity"])
                                if(session["vaccine"]!=''):
                                    datas.append(session["vaccine"])
                                counter =counter + 1

                                # Add the data of particular centre in data list.
                                if(session["available_capacity"]>0):
                                    data.append(datas)
            else:
                print("No response")
        if counter == 0:
            return 0
        return 1
```

下面是 app.py 的完整实现

## 蟒蛇 3

```
from flask import Flask,request,session,render_template
import requests,time
from datetime import datetime,timedelta

app = Flask(__name__)

@app.route('/')
def home():
    return render_template("index.html")

@app.route('/CheckSlot')
def check():

    # fetching pin codes from flask
    pin = request.args.get("pincode")

    # fetching age from flask
    age = request.args.get("age")
    data = list()

    # finding the slot
    result = findSlot(age,pin,data)

    if(result == 0):
        return render_template("noavailable.html") 
    return render_template("slot.html",data = data)

def findSlot(age,pin,data):
    flag = 'y'
    num_days =  2
    actual = datetime.today()
    list_format = [actual + timedelta(days=i) for i in range(num_days)]
    actual_dates = [i.strftime("%d-%m-%Y") for i in list_format]

    # print(actual_dates)
    while True:
        counter = 0
        for given_date in actual_dates:

            # cowin website Api for fetching the data
            URL = "https://cdn-api.co-vin.in/api/v2/appointment/sessions/public/calendarByPin?pincode={}&date={}".format(pin, given_date)
            header = {'User-Agent': 'Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.76 Safari/537.36'}

            # Get the results in json format.
            result = requests.get(URL,headers = header)
            if(result.ok):
                response_json = result.json()
                if(response_json["centers"]):

                    # Checking if centres available or not
                    if(flag.lower() == 'y'):
                        for center in response_json["centers"]:

                            # For Storing all the centre and all parameters
                            for session in center["sessions"]:

                                # Fetching the availability in particular session
                                datas = list()

                                # Adding the pincode of area in list
                                datas.append(pin)

                                # Adding the dates available in list
                                datas.append(given_date)

                                # Adding the centre name in list
                                datas.append(center["name"])

                                # Adding the block name in list
                                datas.append(center["block_name"])

                                # Adding the vaccine cost type whether it is
                                # free or chargable.
                                datas.append(center["fee_type"])

                                # Adding the available capacity or amount of 
                                # doses in list
                                datas.append(session["available_capacity"])
                                if(session["vaccine"]!=''):
                                    datas.append(session["vaccine"])
                                counter =counter + 1

                                # Add the data of particular centre in data list.
                                if(session["available_capacity"]>0):
                                    data.append(datas)

            else:
                print("No response")
        if counter == 0:
            return 0
        return 1

if __name__ == "__main__":
    app.run()
```

**步骤 4:** 现在在模板文件夹中制作三个文件。

*   **index.html:** 显示项目主页，用于输入年龄和 pin 码。
*   **slot.html:** 在页面上显示数据。
*   **不可用. html:** 如果疫苗在任何中心都找不到，那么-没有可用页面。

**index.html 码**

## 超文本标记语言

```
<!doctype html>
<html lang="en">
   <head>
      <!-- Required meta tags -->
      <meta charset="utf-8">
      <meta name="viewport" content="width=device-width, initial-scale=1">
      <!-- Bootstrap CSS -->
      <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/css/bootstrap.min.css" rel="stylesheet"
         integrity="sha384-+0n0xVW2eSR5OomGNYDnhzAbDsOXxcvSN1TPprVMTNDbiYZCxYbOOl7+AMvyTG2x" crossorigin="anonymous">
      <link rel="stylesheet" href="/static/img/style.css">
      <title>Covid Vaccination Slots</title>
   </head>
   <body>
      <h2 class="text-center" style="background-color: rgb(2, 2, 2);padding: 5px;color: white;">Find Your Vaccination Slots
      </h2>
      <div class="container-fluid" style="margin-top: 0px;">
         <div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
            <div class="carousel-inner">
               <div class="carousel-item active" style="height: 350px">
                  <img src="/static/img/geeks.png" class="d-block w-100" alt="...">
               </div>
               <div class="carousel-item" style="height: 350px">
                  <img src="/static/img/geeks.png"
                     class="d-block w-100" alt="...">
               </div>
               <!-- <div class="carousel-item"  style="height: 400px">
                  <img src="/static/img/cor.jpeg" class="d-block w-100" alt="...">
                  </div> -->
            </div>
            <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls"
               data-bs-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
            </button>
            <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls"
               data-bs-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
            </button>
         </div>
      </div>
      <h2 style="text-align: center;margin-top: 50px;">Enter Your Credentials here </h2>
      <div style="margin-left: 620px;margin-top: 10px;">
         <form class="formed" action="/CheckSlot">
            <Label>Pincode</Label>
            <input type="text" name="pincode" placeholder="Enter Your Pincode Here" style="padding: 10px;margin: 5px 5px;border-radius: 5px;"><br>
            <Label>Age</Label>
            <input type="number" name="age" placeholder="Enter Your Age Here" style="padding: 10px;margin: 5px 33px;border-radius: 5px;"><br>
            <input type="submit" style="margin-top: 20px;margin-bottom: 30px;background-color: rgb(26, 151, 224);color: white;padding: 8px;border: 5px;" name="submit" value="Search">
         </form>
      </div>
      <!-- Optional JavaScript; choose one of the two! -->
      <!-- Option 1: Bootstrap Bundle with Popper -->
      <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/js/bootstrap.bundle.min.js"
         integrity="sha384-gtEjrD/SeCtmISkJkNUaaKMoLD0//ElJ19smozuHV6z3Iehds+3Ulb9Bn9Plx0x4"
         crossorigin="anonymous"></script>
      <!-- Option 2: Separate Popper and Bootstrap JS -->
      <!--
         <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js" integrity="sha384-IQsoLXl5PILFhosVNubq5LC7Qb9DXgDA9i+tQ8Zj3iwWAwPtgFTxbJ8NT4GN1R8p" crossorigin="anonymous"></script>
         <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/js/bootstrap.min.js" integrity="sha384-Atwg2Pkwv9vp0ygtn1JAojH0nYbwNJLPhwyoVbhoPwBhjQPR5VtM2+xf0Uwh9KtT" crossorigin="anonymous"></script>
         -->
   </body>
</html>
```

**插槽. html**

## 超文本标记语言

```
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
      <title>Covid Vaccination Slots</title>
   </head>
   <body>
      <h1 style="text-align: center;background-color: black;color: white;">Vaccination Slots Availability</h1>
      <br><br><br><br>
      <div>
         <!-- {% for item in data%}
            {% endfor %} -->
         <table class="table table-hover" style="background-color: aqua;">
            <thead>
               <tr>
                  <th>Pincode</th>
                  <th>Date</th>
                  <th>Vaccination Center Name</th>
                  <th>BlockName</th>
                  <th>Price</th>
                  <th>Available Capacity</th>
                  <th>Vaccine Type</th>
               </tr>
            </thead>
            <tbody>
               {% for item in data%}
               <tr>
                  <td>{{item[0]}}</td>
                  <td>{{item[1]}}</td>
                  <td>{{item[2]}}</td>
                  <td>{{item[3]}}</td>
                  <td>{{item[4]}}</td>
                  <td>{{item[5]}}</td>
                  <td>{{item[6]}}</td>
               </tr>
               {% endfor %}
            </tbody>
         </table>
      </div>
      <h3 style="margin-top: 50px;text-align: center;">
      <a href = "https://www.cowin.gov.in/home">Visit Government Website for Booking Slot</a></h1>
   </body>
</html>
```

不可操作. html

## 超文本标记语言

```
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>No Availablity</title>
   </head>
   <p style="text-align: center;font-size: 150px;color: rgb(255, 136, 0);">Sorry !</p>

   <body>
      <h1 style="text-align: center;color: red;margin: 0 auto;">No Available Vaccine Slots</h1>
   </body>
</html>
```

将图像或其他文件(如果有)添加到静态文件夹中。

<video class="wp-video-shortcode" id="video-677273-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210831095055/Covid-vaccination.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210831095055/Covid-vaccination.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210831095055/Covid-vaccination.mp4)</video>
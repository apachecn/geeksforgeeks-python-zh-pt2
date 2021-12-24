# 从 Firebase 搜索 Django 中的数据

> 原文:[https://www . geesforgeks . org/search-data-in-django-from-firebase/](https://www.geeksforgeeks.org/search-data-in-django-from-firebase/)

**Firebase** 是谷歌的一款产品，帮助开发者轻松构建、管理和开发他们的应用。它帮助开发者以更快、更安全的方式构建他们的应用程序。在 firebase 端不需要编程，这使得更有效地使用它的特性变得容易。它提供云存储。它使用 NoSQL 存储数据。

在这里，我们将学习如何在 Firebase 中搜索数据。为此，请遵循以下步骤:

**第一步:**如果你是火焰基地的新手，那么请参考[这个](https://www.geeksforgeeks.org/create-a-website-using-html-css-and-javascript-that-stores-data-in-firebase/)。

**第二步:**转到**URL . py**文件，创建一个路径，移动到网页上搜索数据。

## 计算机编程语言

```
from django.contrib import admin
from django.urls import path
from . import views

urlpatterns = [

    #when we are moving to search then move to this url
    path('search/', views.search),

    #showing search detail on this url
    path('searchusers/', views.searchusers),
]
```

**第三步:**然后转到**view . py**文件，编写如下函数渲染到 html 页面。

## 计算机编程语言

```
from django.shortcuts import render
from django.views.decorators.http import require_http_methods
from django.views.decorators.csrf import csrf_exempt
from django.contrib.auth.decorators import login_required
import pyrebase

config={

    "databaseURL": "*********************",
    "projectId": "*******************",

}
firebase=pyrebase.initialize_app(config)
authe = firebase.auth()
database=firebase.database()

# move to this search.html page to search for content
def search(request):
    return render(request, "search.html")

# after typing what to search this function will be called
def searchusers(request):
    value = request.POST.get('search')

    # if no value is given then render to search.h6tml
    if value =="":
        return render(request, "search.html")
    title = request.POST['category']
    if title =="":
        return render(request, "search.html")
    if value is None or title is None:
        print(value ,"Value",title)
        return render(request, "search.html")
    else:
        if title == "Users":
            data = database.child('users').shallow().get().val()
            uidlist = []
            requid = 'null'

            # append all the id in uidlist
            for i in data:
                uidlist.append(i)

            # if we have find all the uid then
            # we will look for the one we need   
            for i in uidlist:
                val = database.child('users').child(i).child('name').get().val()
                val=val.lower()
                value=value.lower()
                print(val,value)

                # if uid we want is value then
                # we will store that in requid
                if (val == value):
                    requid = i
            if requid=='null':
                return render(request, "search.html")
            print(requid)

            # then we will retrieve all the data related to that uid
            name = database.child('users').child(requid).child('name').get().val()
            course = database.child('users').child(requid).child('course').get().val()
            branch = database.child('users').child(requid).child('branch').get().val()
            img = database.child('users').child(requid).child('imgUrl').get().val()
            Name = []
            Name.append(name)
            Course = []
            Course.append(course)
            Branch = []
            Branch.append(branch)
            Image = []
            Image.append(img)
            comb_lis = zip(Name, Course, Branch, Image)

            # send all data in zip form to searchusers.html
            return render(request, "SearchUsers.html", {"comb_lis": comb_lis})
```

**第四步:**然后我们会移动到**search.html**页面，并编写以下代码在 firebase 中搜索数据。评论写在里面，以便更好地理解。

## 超文本标记语言

```
{% load static %}
<html lang="en">
   <head>
      <title>Search Page</title>
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
      <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>
      <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
      <link rel='stylesheet' href="{% static '/css/Search.css' %}">
      <link rel="stylesheet" type="text/css" href="{%static '/css/footer.css' %}">
   </head>
   <body>
      <div class="container">
         <div class="inner">
            <form method="post" action="/searchusers/">
               {% csrf_token %}
               <!--Type the name you want to search and click on submit-->
               <input type="text" placeholder="Enter Title..." aria-label="Search.." name="search"
                  id="search">
               <select name="category" id="category" name="">
                  <option value="">Select Category</option>
                  <!--select type to user-->
                  <option value="Users">Users</option>
               </select>
               <input type="submit" value="Find">
            </form>
         </div>
      </div>
   </body>
</html>
```

**第五步:**然后我们会移动到*searchusers.html*页面，它会在网页上显示检索到的数据，如输出所示。

## 超文本标记语言

```
{% load static %}
<html lang="en">
   <head>
      <title>User's List</title>
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
      <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>
      <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
      <link rel='stylesheet' href="{% static '/css/Search.css' %}">
   </head>
   <body>
      <div class="tm-container">
         <div class="tm-main-content">
            <section class="tm-section tm-section-small text-center">
               <!--Showing all the details we retrieved Here-->
               {% for name,course,branch,image in comb_lis %}
               <h1>Here are the results:</h1>
               <div class="image">
                  <img src="{{image}}" alt="Profile">
                  <h3 class="tm-section-header3">Name: {{name}}</h3>
                  <h3 class="tm-section-header2">Course: {{ course }},  {{ branch }}  </h3>
               </div>
               {% endfor %}
            </section>
         </div>
         <br>
      </div>
   </body>
</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-592043-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210315000536/20210315_000309.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210315000536/20210315_000309.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210315000536/20210315_000309.mp4)</video>
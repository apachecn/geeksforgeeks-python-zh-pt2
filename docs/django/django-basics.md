# 姜戈基础

> 原文:[https://www.geeksforgeeks.org/django-basics/](https://www.geeksforgeeks.org/django-basics/)

Django 是一个基于 Python 的 web 框架，它允许您快速创建 web 应用程序，而没有其他框架通常会遇到的所有安装或依赖问题。
当你在构建一个网站时，你总是需要一组相似的组件:一种处理用户身份验证(注册、登录、注销)的方式，一个网站、表单的管理面板，一种上传文件的方式等。Django 为您提供现成的组件供您使用。

![django-basics](img/f6ea6c353beb43c75dc19b2d4af13013.png)

#### 为什么是姜戈？

*   Django 是一个快速的 web 开发框架，可以用来在短时间内开发完全充实的 web 应用程序。
*   在 Django 框架中切换数据库非常容易。
*   它有内置的管理界面，这使得它很容易工作。
*   Django 是一个功能齐全的框架，不需要其他东西。
*   它有数千个额外的软件包可用。
*   它是非常可扩展的。更多请访问[何时使用 Django？与其他开发栈的比较？](https://www.geeksforgeeks.org/when-to-use-django-comparison-with-other-development-stacks/)

#### 姜戈建筑

Django 基于 MVT(模型-视图-模板)架构。MVT 是一个开发 web 应用程序的软件设计模式。

MVT 结构由以下三部分组成

**模型**:模型将作为你数据的接口。它负责维护数据。它是整个应用程序背后的逻辑数据结构，由数据库(通常是关系数据库，如 MySql、Postgres)表示。

**视图**:视图是用户界面——渲染网站时在浏览器中看到的内容。它由 HTML/CSS/Javascript 和 Jinja 文件表示。

**模板**:模板由所需 HTML 输出的静态部分以及一些描述如何插入动态内容的特殊语法组成。

要查看更多关于姜戈建筑的信息，请访问[姜戈项目 MVT 结构](https://www.geeksforgeeks.org/django-project-mvt-structure/)

#### 安装 Django

*   Install python3 if not installed in your system ( according to configuration of your system and OS) from [here](https://www.python.org/downloads/) . Try to download the latest version of python it’s python3.6.4 this time.

    **注意-**Django 在 Linux 和 mac 中的安装是类似的，这里我是在 windows 中展示的对于 Linux 和 Mac 来说只需要打开终端代替命令提示符，并通过以下命令。

*   **安装 pip-** 打开命令提示符，输入以下命令-

    ```
    python -m pip install -U pip
    ```

*   **安装虚拟环境-** 在 cmd 中输入以下命令-

    ```
    pip install virtualenv
    ```

*   **设置虚拟环境-** 设置虚拟环境将允许您编辑依赖关系，这通常是您的系统不允许的。
    按照以下步骤设置虚拟环境-
    1.  通过在 cmd 中给出以下命令来创建虚拟环境-

        ```
        virtualenv env_site
        ```

    2.  通过此命令将目录更改为 env _ site-

        ```
        cd env_site
        ```

    3.  转到 env_site 内的脚本目录，激活虚拟环境-

        ```
        cd Script
        ```

        ```
        activate
        ```

*   **Install Django-** Install django by giving following command-

    ```
    pip install django
    ```

    ![](img/0113040582552ed5f19396182d03a4aa.png)

    #### 创建项目

    让我们来看看在你的电脑上安装了 Django 之后，如何使用它创建一个基本的项目。

    *   要在您的电脑上启动姜戈项目，打开终端并输入以下命令

        ```
        django-admin startproject projectName
        ```

    *   A New Folder with name projectName will be created. To enter in the project using terminal enter command

        ```
        cd projectName
        ```

        现在快跑，

        ```
        Python manage.py runserver
        ```

        现在访问 [http://localhost:8000/](http://localhost:8000/) 、
        T3】

        #### 创建应用程序

        Django 以其独特且全面管理的应用程序结构而闻名。对于每一项功能，应用程序都可以像一个完全独立的模块一样创建。本文将带您了解如何创建一个基本的应用程序，并使用该应用程序添加功能。

        *   To create a basic app in your Django project you need to go to directory containing `manage.py` and from there enter the command :

            ```
            python manage.py startapp projectApp
            ```

            现在您可以看到您的目录结构如下:

            ![](img/2e8dfadc57fb5f17698883f214abb2ab.png)

        *   要考虑项目中的应用程序，您需要在 INSTALLED_APPS 列表中指定您的项目名称，如下所示
        *   So, we have finally created an app but to render the app using urls we need to include the app in our main project so that urls redirected to that app can be rendered. Let us explore it.
            Move to `projectName-> projectName -> urls.py` and add below code in the header

            ```
            from django.urls import include 
            ```

            现在，在网址模式列表中，您需要指定应用名称来包含您的应用网址。这是它的代码

            ```
            from django.contrib import admin
            from django.urls import path, include

            urlpatterns = [
                path('admin/', admin.site.urls),
                # Enter the app name in following syntax for this to work
                path('', include("projectApp.urls")),
            ]
            ```

        *   现在你可以使用默认的 MVT 模型来创建网址、模型、视图等。它们会自动包含在你的主项目中。

Django Apps 的主要特点是独立性，每一个 app 都作为一个独立的单元来支持主项目。想了解更多关于 Django 的应用，请访问[如何在 Django 创建应用？](https://www.geeksforgeeks.org/how-to-create-an-app-in-django/)

#### 关于姜戈的更多信息–

[Django Models](https://www.geeksforgeeks.org/django-models/)

[Django Forms](https://www.geeksforgeeks.org/django-forms/)

[Django Views](https://www.geeksforgeeks.org/views-in-django-python/)

[Django Templates](https://www.geeksforgeeks.org/django-templates/)
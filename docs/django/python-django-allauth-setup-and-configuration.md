# Python | Django-allaus 设置和配置

> 原文:[https://www . geesforgeks . org/python-django-alla uth-setup-and-configuration/](https://www.geeksforgeeks.org/python-django-allauth-setup-and-configuration/)

用户注册是 web 应用程序最重要的部分之一。`django-registration-redux`和`django-alluth`是姜戈最著名的注册应用。本教程系列涉及`django-allauth`的设置、配置和定制，并为希望快速开始使用`allauth`的新用户提供指导，并在此过程中轻松进行有用的定制。

本文介绍设置和一些基本配置。后面我们会处理社交登录、扩展类以及高效利用`DefaultAccountAdapter`添加自定义流程。

对于`django`新手或`django-allauth`本身的新用户来说，这可能是压倒性的。虽然它被很好地记录下来，但是由于所涉及的开发人员的时间和资源限制，关于这个库的文章和深入的教程并不多。因此，本系列试图解决这个问题，并制作一个全面的指南系列，使`django-allauth`易于使用和 django 社区的工作。

**如何设置？**
你可以[下载](https://github.com/gajeshbhat/django-experiments/tree/master/allauthdemo)教程中用到的文件，抢先一步。以下步骤将指导您完成设置。

*   创建一个姜戈项目，如果你还没有的话。
*   使用命令`pip install django-allauth`安装`django-allauth`
*   添加`'allauth`、`allauth.account'`、`allauth.socialaccount`以及所有必要的社交登录到`INSTALLED_APPS.`你可以在这里查看支持的 API 的整个列表[。社交登录功能将在下一篇文章中详细描述。在您配置您安装的应用程序后，应该如下所示。](http://django-allauth.readthedocs.io/en/latest/installation.html)

```py
INSTALLED_APPS = [
    'django.contrib.admin',
    'allauth',
    'allauth.account',
    'allauth.socialaccount',
    'allauth.socialaccount.providers.google',
    'allauth.socialaccount.providers.facebook',
    'django.contrib.auth',
    'django.contrib.sites',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
```

*   在`settings.py`中配置`template`上下文处理器设置，并在项目

    ```py
    TEMPLATES = [
      {
            'BACKEND': 'django.template.backends.django.DjangoTemplates',
            'DIRS': [
                os.path.normpath(os.path.join(BASE_DIR, 'templates')),
            ],
            'APP_DIRS': True,
            'OPTIONS': {
                'context_processors': [
                    'django.template.context_processors.debug',
                    'django.template.context_processors.request',
                    'django.contrib.auth.context_processors.auth',
                    'django.contrib.messages.context_processors.messages',
                    'django.template.context_processors.request',
                ],
            },
        },
    ]
    ```

    中添加网址模式
*   添加以下身份验证后端。

    ```py
    AUTHENTICATION_BACKENDS = (
        'django.contrib.auth.backends.ModelBackend',
        'allauth.account.auth_backends.AuthenticationBackend',
    )
    ```

*   从 django-allaus 资源库或我的[自定义资源库](https://github.com/gajeshbhat/django-experiments/tree/master/allauthdemo/templates)中复制模板文件(我做了一些修改和一些良好的结构化)，并将其粘贴到项目目录的`templates`文件夹中。
*   Add the allauth urls in `urls.py` of your main project directory. After adding the allauth urls the below should look like,

    ```py
    from django.contrib import admin
    from django.urls import path
    from django.conf.urls import url, include
    urlpatterns = [
        path('admin/', admin.site.urls),
        url(r'^accounts/', include('allauth.urls')),
    ]
    ```

    *   您也可以自己添加自定义 CSS，或者添加我在使用 allauth 模板时创建的我的 CSS(有很好的注释和文档)。它包括几乎所有页面的样式，甚至包括用于确认和密码重置电子邮件的移动友好电子邮件模板。您可以通过在项目目录中创建一个`static`文件夹并将 CSS 放在`account`文件夹中来实现。
    *   运行`python manage.py makemigrations`和`python manage.py migrate`以运行所有必要的迁移，并运行`python manage.py runserver`以启动 django 服务器。
    *   按照网址模式显示注册表单。
        如:`localhost:8000/accounts/login`显示登录页面。

    **配置:**
    大多数 django-allaus 特性都可以通过将内置适配器和变量放在`settings.py.`文件中来配置。虽然[文档](http://django-allauth.readthedocs.io/en/latest/configuration.html)有大量这样的选项和很好的解释，但强调了下面一些重要的选项。

    *   电子邮件确认到期:设置帐户需要激活的天数。例:`ACCOUNT_EMAIL_CONFIRMATION_EXPIRE_DAYS=7`
    *   激活需要电子邮件:此选项允许您设置是否需要电子邮件地址来注册。设置`False`禁用电子邮件要求。例:`ACCOUNT_EMAIL_REQUIRED = True`
    *   账户邮件验证:该选项可用于设置用户注册账户后登录是否需要进行邮件验证。您可以使用“强制”来阻止用户登录，直到电子邮件得到验证。您可以设置`optional`发送电子邮件，但允许用户在没有电子邮件的情况下登录。也可以设置`none`不发送任何验证邮件。(不推荐)例如:`ACCOUNT_EMAIL_VERIFICATION = "mandatory"`
    *   登录尝试限制:这是一个重要的特性，可以用来防止对所有验证中的用户登录模块的暴力攻击。可以设置登录尝试的最大次数，并且在超时之前阻止用户登录。该功能利用`ACCOUNT_LOGIN_ATTEMPTS_TIMEOUT`设置。例:`ACCOUNT_LOGIN_ATTEMPTS_LIMIT = 5`
    *   登录尝试限制超时:该设置需要与`ACCOUNT_LOGIN_ATTEMPTS_LIMIT`设置一起使用。设置的值是从上次不成功的登录尝试开始的秒数。请不要认为这不会阻止管理员登录被暴力强制。例:`ACCOUNT_LOGIN_ATTEMPTS_TIMEOUT = 86400 # 1 day in seconds`
    *   登录和注销网址重定向:当用户登录或注销时，您可能希望将用户重定向到特定的网址或页面，以下设置可用于设置这些值。默认情况下，所有登录将重定向至`/accounts/profile/`网址，注销将重定向至`localhost:8000`或任何`localhost`主页。
        Eg:`ACCOUNT_LOGOUT_REDIRECT_URL ='/accounts/login/'`T6】Eg:`LOGIN_REDIRECT_URL = '/accounts/email/'`

    最后，您的`allauth` 设置应该看起来类似于下面的设置。

    ```py
    #django-allauth registraion settings
    ACCOUNT_EMAIL_CONFIRMATION_EXPIRE_DAYS =1
    ACCOUNT_EMAIL_REQUIRED = True
    ACCOUNT_EMAIL_VERIFICATION = "mandatory"
    ACCOUNT_LOGIN_ATTEMPTS_LIMIT = 5

    # 1 day
    ACCOUNT_LOGIN_ATTEMPTS_TIMEOUT = 86400 

    #or any other page
    ACCOUNT_LOGOUT_REDIRECT_URL ='/accounts/login/' 

    # redirects to profile page if not configured.
    LOGIN_REDIRECT_URL = '/accounts/email/'
    ```

    **参考资料** :
    [姜戈-阿拉鲁斯官方文档](http://django-allauth.readthedocs.io/en/latest/)
    [我的自定义模板和 css](https://github.com/gajeshbhat/django-experiments/tree/master/allauthdemo)
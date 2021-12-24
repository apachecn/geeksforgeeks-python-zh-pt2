# 序列化程序关系–姜戈 REST 框架

> 原文:[https://www . geesforgeks . org/serializer-relations-django-rest-framework/](https://www.geeksforgeeks.org/serializer-relations-django-rest-framework/)

序列化是 RESTful 网络服务中最重要的概念之一。它有助于将复杂数据(如模型实例)转换为本机 Python 数据类型，这些数据类型可以使用 JSON、XML 或其他内容类型呈现。在 Django REST 框架中，我们有不同类型的[序列化器](https://www.geeksforgeeks.org/serializers-django-rest-framework/)来序列化对象实例，序列化器有不同的序列化器关系来表示模型关系。在本节中，我们将讨论 Django REST 框架序列化程序提供的不同序列化程序关系。

> **目录**
> 
> *   [Introduction](#getting_started)
> *   [Create Jiang Ge model and view](#create)
> *   [原发性心动过速域](#PrimaryKeyRelatedField)
> *   [StringRelatedField](#StringRelatedField)
> *   slagerlatedfeld
> *   [超连结编辑栏位](#HyperlinkedIndetityField)

## 入门指南

在使用 Django REST 框架序列化程序之前，您应该确保已经在虚拟环境中安装了 Django 和 Django REST 框架。您可以查看以下教程:

*   [使用 venv | Python 创建虚拟环境](https://www.geeksforgeeks.org/create-virtual-environment-using-venv-python/)
*   姜戈安装
*   [Django REST 框架安装](https://www.geeksforgeeks.org/django-rest-framework-installation/)

接下来，您可以创建一个名为 emt(员工管理工具)的项目和一个名为 employees 的应用程序。请参考以下文章，查看如何在 Django 中创建项目和应用程序。

*   [How to use MVT in Jiang Ge to create basic projects?](https://www.geeksforgeeks.org/how-to-create-a-basic-project-using-mvt-in-django/)
*   [How to create an App in Jiang Ge?](https://www.geeksforgeeks.org/how-to-create-an-app-in-django/)

在本节中，我们将使用 PostgreSQL。您必须在 PostgreSQL 中创建一个名为 emt 的数据库。您可以查看下面的安装链接。

[在 Windows 上安装 PostgreSQL](https://www.geeksforgeeks.org/install-postgresql-on-windows/)

> 注意:如果需要使用 SQLite，可以继续使用默认数据库。

为了利用 PostgreSQL，我们需要安装一个 Python-PostgreSQL 数据库适配器(psycopg2)。这个包帮助 Django 与 PostgreSQL 数据库进行交互。您可以使用下面的命令来安装 psycopg2 包。确保 PostgreSQL bin 文件夹包含在 PATH 环境变量中，并且虚拟环境在执行命令之前被激活。

> pip 安装 psycopg2

现在，您需要在您的 Django 项目中配置 PostgreSQL 数据库。默认情况下，数据库配置有一个 SQLite 数据库引擎和数据库文件名。您可以检查 setting.py Python 文件，并用 PostgreSQL 数据库配置替换默认数据库配置。

```
DATABASES = {
   'default': {
       'ENGINE': 'django.db.backends.postgresql',
       'NAME': 'emt',
       'USER': 'username',
       'PASSWORD': 'password',
       'HOST': '127.0.0.1',
       'PORT': '5432',
   }
}
```

这里，名称指的是数据库名称，用户和密码指的是 Postgres 用户名和密码。

最后，我们需要在虚拟环境中安装 httpie 包。我们将为 CRUD 操作编写 HTTPie 命令。您可以激活虚拟环境并运行以下命令

> pip install–升级 httpie

## 创建姜戈模型和视图

### 创建姜戈模型

在 Django 中，[模型](https://www.geeksforgeeks.org/django-models/)是以面向对象的方式处理数据库的类。每个模型类引用一个数据库表，模型类中的每个属性引用一个数据库列。在这里，我们将在 Django 创建一个 Employee 模型和 EmployeeTask 模型。EmployeeTask 模型与 Employee 模型有许多相似的关系我们要求我们的 Employee 实体具有以下属性:

*   emp_id
*   (full) name
*   gender
*   title

我们的 employee 任务模型的属性如下:

*   Character name
*   Employee (foreign key–employee)
*   Task _desc
*   Creation _ date
*   expiration date

让我们开始在姜戈实现雇员模型。可以用下面的代码替换 models.py Python 文件:

## Python 3

```
GENDER_CHOICES = (('M','Male'),
                      ('F','Female'),)

class Employee(models.Model):
    emp_id = models.IntegerField()
    name = models.CharField(max_length=150)
    gender = models.CharField(max_length=1,
                              choices=GENDER_CHOICES,
                              default='M')
    designation = models.CharField(max_length=150)

    class Meta:
        ordering=('emp_id',)

    def __str__(self):
        return self.name
```

雇员模型是 django.db.models.Model 类的子类，定义了属性和元内部类。它有一个排序属性，根据员工 id 以升序对结果进行排序。

接下来，让我们进入 EmployeeTask 模型的实现。您可以将下面的代码添加到 models.py 文件中。

## 蟒 3

```
class EmployeeTask(models.Model):
    task_name = models.CharField(max_length=150)
    employee = models.ForeignKey(Employee,
                                  related_name='tasks',
                                  on_delete=models.CASCADE)
    task_desc = models.CharField(max_length=350)
    created_date = models.DateTimeField(auto_now_add=True)
    deadline = models.DateTimeField()

    class Meta:
        ordering = ('task_name',)

    def __str__(self):
        return self.task_name
```

EmployeeTask 模型是 django.db.models.Model 类的子类，定义了属性和一个 Meta 内部类。它有一个排序属性，根据 task_name 以升序对结果进行排序。它有一个员工字段，与员工模型保持多对一的关系。

```
employee = models.ForeignKey(Employee,
                                  related_name='tasks',
                                  on_delete=models.CASCADE)
```

related_name 有助于建立反向关系。反向关系是指从员工转到员工任务。员工字段表示员工详细信息表中的员工模型。同样，相关名称表示雇员模型中的雇员任务。

序列化程序类不会自动包含反向关系。我们必须将其明确添加到字段列表中。如果在关系上设置了适当的 related_name 参数，则可以将其用作字段名(在序列化模型时，您将能够理解反向关系)。

让我们使用下面的命令进行初始迁移。

> 巨蟒迁徙

如果迁移成功，则使用以下命令应用所有生成的迁移:

> python manage . py migrate

如果成功，您可以检查您的数据库条目。现在，让我们创建姜戈视图。

### 创建视图

Django 视图便于处理 HTTP 请求和提供 HTTP 响应。在接收到一个 HTTP 请求时，Django 创建一个 HTTP request 实例，并将它作为第一个参数传递给视图函数。视图函数检查该值，并基于 HTTP 谓词执行代码。这里的代码使用@ csrf _ exclude 装饰器来设置一个 csrf(跨站点请求伪造)cookie。这使得从没有 CSRF 令牌的客户端发布到此视图成为可能。

您可以将下面的代码添加到 view.py 文件中。

## 蟒 3

```
from django.shortcuts import render
from django.http import HttpResponse, JsonResponse
from django.views.decorators.csrf import csrf_exempt

from rest_framework.renderers import JSONRenderer
from rest_framework.parsers import JSONParser

from employees.models import Employee, EmployeeTask
from employees.serializers import EmployeeSerializer, EmployeeTaskSerializer

@csrf_exempt
def employee_list(request):
    if request.method == 'GET':
        emp = Employee.objects.all()
        emp_serializer = EmployeeSerializer(emp, many=True)
        return JsonResponse(emp_serializer.data, safe=False)

    elif request.method == 'POST':
        emp_data = JSONParser().parse(request)
        emp_serializer = EmployeeSerializer(data=emp_data)

        if emp_serializer.is_valid():
            emp_serializer.save()
            return JsonResponse(emp_serializer.data,
                                status=201)
        return JsonResponse(emp_serializer.errors,
                            status=400)

@csrf_exempt
def employee_detail(request, pk):
    try:
        emp = Employee.objects.get(pk=pk)
    except Employee.DoesNotExist:
        return HttpResponse(status=404)

    if request.method == 'GET':
        emp_serializer = EmployeeSerializer(emp)
        return JsonResponse(emp_serializer.data)
    elif request.method == 'DELETE':
        emp.delete()
        return HttpResponse(status=204)

@csrf_exempt
def employeetask_list(request):
    if request.method == 'GET':
        emptask = EmployeeTask.objects.all()
        emptask_serializer = EmployeeTaskSerializer(emptask, many=True)
        return JsonResponse(emptask_serializer.data, safe=False)
    elif request.method == 'POST':
        emptask_data = JSONParser().parse(request)
        emptask_serializer = EmployeeTaskSerializer(data=emptask_data)
        if emptask_serializer.is_valid():
            emptask_serializer.save()
            return JsonResponse(emptask_serializer.data,
                                status=201)
        return JsonResponse(emptask_serializer.errors,
                            status=400)

@csrf_exempt
def employeetask_detail(request, pk):
    try:
        emptask = EmployeeTask.objects.get(pk=pk)
    except EmployeeTask.DoesNotExist:
        return HTTPResponse(status=404)

    if request.method == 'GET':
        emptask_serializer = EmployeeTaskSerializer(emptask)
        return JsonResponse(emptask_serializer.data)

    elif request.method == 'DELETE':
        emptask.delete()
        return HttpResponse(status=204)
```
# 在 API-Django REST 框架中添加权限

> 原文:[https://www . geesforgeks . org/add-permission-in-API-django-rest-framework/](https://www.geeksforgeeks.org/adding-permission-in-api-django-rest-framework/)

当涉及到访问控制时，有许多不同的场景需要考虑。允许未经授权访问有风险的操作或受限区域会导致巨大的漏洞。这突出了在 API 中添加权限的重要性。

Django REST 框架允许我们利用权限来定义哪些内容可以被访问，哪些操作可以以有意义或通用的方式执行。权限检查总是在每个视图的开头运行。它使用每个传入请求的“request.user”和“request.auth”属性中的身份验证信息。如果权限检查失败，则视图代码将不会运行。

**注意:**权限与身份验证一起决定了是授予还是拒绝对传入请求的访问。在本节中，我们将把[基本身份验证](https://write.geeksforgeeks.org/post/2737873)与 Django REST 框架权限结合起来设置访问控制。您可以参考 Django REST 框架中的[可浏览 API 来获取模型、序列化程序和视图](https://www.geeksforgeeks.org/browsable-api-in-django-rest-framework/)

让我们深入挖掘一下 Django REST 框架权限。

*   Permission allowed
*   authentication
*   Authenticate user
*   Authentication rights only
*   Jiang Ge model permissions
*   Jiang Ge Model Permission Soran is read-only.
*   Jiang Ge object permissions

## 允许任何

allowyy 权限类将允许不受限制的访问，不管请求是经过身份验证的还是未经身份验证的。这里权限设置默认为无限制访问

```py
'DEFAULT_PERMISSION_CLASSES': [
   'rest_framework.permissions.AllowAny',
]
```

不需要设置这个权限，但建议提一下，让意图明确。除了全局提及之外，您还可以基于每个视图设置权限策略。如果使用的是基于 APIView 类的视图，代码如下

## python 3

```py
from rest_framework.permissions import AllowAny
from rest_framework.response import Response
from rest_framework.views import APIView

class ClassBasedView(APIView):
    permission_classes = [AllowAny]

    def get(self, request, format=None):
        content = {
            'status': 'request was permitted'
        }
        return Response(content)
```

使用带有基于函数的视图的@api_view 装饰器时，代码如下:

## python 3

```py
from rest_framework.decorators import api_view, permission_classes
from rest_framework.permissions import AllowAny
from rest_framework.response import Response

@api_view(['GET'])
@permission_classes([AllowAny])
def function_view(request, format=None):
    content = {
        'status': 'request was permitted'
    }
    return Response(content)
```

## 通过身份验证

IsAuthenticated 权限类拒绝未经身份验证的用户使用 API 进行任何操作。这确保了只有注册用户才能访问 API。让我们在 RESTful web 服务中使用 IsAuthenticated 类。在这里，我们可以基于每个视图设置权限策略。让我们在我们的机器人细节和机器人列表类中导入并添加权限类。代码如下:

```py
from rest_framework.permissions import IsAuthenticated
```

## 蟒 3

```py
class RobotDetail(generics.RetrieveUpdateDestroyAPIView):
    permission_classes = [IsAuthenticated]
    queryset = Robot.objects.all()
    serializer_class = RobotSerializer
    name = 'robot-detail'

class RobotList(generics.ListCreateAPIView):
    permission_classes = [IsAuthenticated]
    queryset = Robot.objects.all()
    serializer_class = RobotSerializer
    name = 'robot-list'
```
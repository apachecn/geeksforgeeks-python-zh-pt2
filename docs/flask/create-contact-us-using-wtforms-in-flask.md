# 使用烧瓶中的表格

创建联系我们

> 原文:[https://www . geesforgeks . org/create-contact-us-using-wtforms-in-flask/](https://www.geeksforgeeks.org/create-contact-us-using-wtforms-in-flask/)

**WTForms** 是一个旨在使表单处理更容易管理的库。它非常容易处理浏览器提交的数据。在本文中，我们将讨论如何使用 WTForms 创建联系我们表单。

### **WT-FORM 的优势:**

1.  我们不必担心验证器。
2.  避免[跨站点请求伪造(CSRF)](https://en.wikipedia.org/wiki/Cross-site_request_forgery) 。
3.  WTForms 以类的形式出现，所以所有的好东西都来自一个对象形式。
4.  无需使用 HTML 手动创建任何<label>或<input>元素。</label>

### 装置

使用终端安装烧瓶-WTF。

```
pip install Flask-WTF
```

### 逐步实施

**第一步:**在**主页面**创建一个包含你想要的所有元素的类。

## 蟒蛇 3

```
from flask_wtf import FlaskForm
from wtforms import StringField, validators, PasswordField, SubmitField
from wtforms.validators import DataRequired, Email
import email_validator

class contactForm(FlaskForm):
    name = StringField(label='Name', validators=[DataRequired()])
    email = StringField(label='Email', validators=[
      DataRequired(), Email(granular_message=True)])
       message= StringField(label='Message')
    submit = SubmitField(label="Log In")
```

**步骤 2:** 创建表单的对象，并将该对象作为参数传递到 render_template 中

## python 3

```
@app.route("/", methods=["GET", "POST"])
def home():
    cform = contactForm()
    return render_template("contact.html", form=cform)
```

**第三步:**增加 CSRF 保护。添加密钥。

```
app.secret_key = "any-string-you-want-just-keep-it-secret"
```

**步骤 4:** 添加 contact.html HTML 文件中的字段。

```
{{ form.csrf_token }} is used to provide csrf protection.
```

## HTML

```
<!DOCTYPE HTML>

<html>
    <head>
        <title>Contact</title>
    </head>
    <body>
        <div class="container">
            <h1>Contact Us</h1>
            <form method="POST" action="{{ url_for('home') }}">
                {{ form.csrf_token }}

                <p>
                    {{ form.name.label }} 
                    <br>
                    {{ form.name }}
                </p>

                <p>
                    {{ form.email.label }} 
                    <br>
                    {{ form.email(size=30) }}
                </p>

                <p>
                    {{ form.message.label }} 
                    <br>
                    {{ form.message }}
                </p>

                {{ form.submit }}
            </form>
        </div>
    </body>
</html>
```

**步骤 5:** 验证表单并接收数据。

## 蟒 3

```
@app.route("/", methods=["GET", "POST"])
def home():
    cform = contactForm()
    if cform.validate_on_submit():
        print(f"Name:{cform.name.data}, 
              E-mail:{cform.email.data}, 
              message:{cform.message.data}")
    else:
        print("Invalid Credentials")

    return render_template("contact.html", form=cform)
```
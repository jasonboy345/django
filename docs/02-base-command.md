#django manage.py 命令

## 创建django项目 

```
django-admin.py startproject project-name
```

## 新建app 

```
python manage.py startapp app-name
```

## 同步数据库
```
python manage.py makemigrations
python manage.py migrate
```
以上命令可以往数据库添加表，当你在 `models.py` 中新增类时，运行它就可以自动在数据库中创建表，不用手动创建。

## 启动django web服务
```
# 默认情况下在 0.0.0.0:8080 启动
python manage.py runserver 

# 当提示端口被占用的时候，可以用其他端口
```
通过127.0.0.1:8080访问页面

## 清空数据库
```
python manage.py flush
```
此命令会询问是 yes 还是 no，选择 yes 会把数据库全部清空掉，只留下空表

## 创建超级管理员
```
# 按照提示输入用户名和对应的密码可以，邮箱可以留空，用户名和密码必填
python manage.py createsuperuser

# 修改用户密码可以使用以下命令
python manage.py changepassword username
```

## 导出数据库 导入数据库
```
# 导出appname应用的数据
python manage.py dumpdata appname > appname.json
# 导入appname应用的数据
python manage.py loaddata appname.json
# 导出所有的数据
python manage.py dumpdata > mysite_all_data.json
# 导入所有的数据
python manage.py loaddata mysite_all_data.json
```

## Django 项目环境终端
```
python manage.py shell
```
这个命令和直接运行 python 进入 shell 的区别是：你可以在这个 shell 里面调用当前项目的 models.py 中的 API，对于操作数据，还有一些小测试非常方便。_第六章模型和数据库可以看到__

## 更多manage.py命令
直接在终端上输入以下命令，可以看到详细的列表，在忘记参数名时特别有用
```
python manage.py
```
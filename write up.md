# web write up



## 1.Training-WWW-Robots

输入/robots.txt

然后打开fl0g.php就可以看到flag:`wWwrobots`

## 2.view_source

1.用firefox打开页面，摁下F12，打开查看器可以得到flag

2.或用chrome打开页面，摁下F12，在Elements栏可以得到flag

## 3.get_post

1.打开hackbar，用get方式传递a=1.

2.勾选hackbar上的Enable post data，用post方式传递b=2，可获得flag

## 4.robots

1.根据提示robots,可以直接想到robots.txt,

2.或通过扫目录也可以扫到: `python dirsearch.py -u http://10.10.10.175:32793/ -e *`

3.访问`http://111.198.29.45:33982/robots.txt`发现`f1ag_1s_h3re.php`

4.访问`http://111.198.29.45:33982/f1ag_1s_h3re.php`

## 5.cookie

1.浏览器按下F12键打开开发者工具，刷新后，在存储一栏，可看到名为look-here的cookie的值为cookie.php

2.访问`http://111.198.29.45:47911/cookie.php`，提示查看http响应包，在网络一栏，可看到访问cookie.php的数据包

3.点击查看数据包，在消息头内可发现flag

## 6.disabled_button

1.打开开发者工具，在查看器窗口审查元素，发现存在disabled=""字段，

2.将`disabled=""`删除后，按钮可按，按下后得到flag

3.或审计from表单代码，使用hackbar，用post方式传递auth=flag，同样可以获得flag

## 7.weak_auth

1.随便输入下用户名和密码,提示要用admin用户登入,然后跳转到了check.php,查看下源代码提示要用字典。

2.用Yakit截下登录的数据包,把数据包发送到intruder爆破

2.设置爆破点为password

3.加载字典

4.开始攻击，查看响应包列表，发现密码为123456时，响应包的长度和别的不一样.

5.点进去查看响应包，获得flag



![Cache_45dac01c2b56a9ec](D:/Cache_45dac01c2b56a9ec.jpg)

注：在线环境不知道为什么创建不了![屏幕截图 2024-11-26 222041](../../../Pictures/Screenshots/屏幕截图 2024-11-26 222041.png)了，配不了图，长期沉迷于学c和cpp，web仅停留初学阶段，勿喷小登（哭）。
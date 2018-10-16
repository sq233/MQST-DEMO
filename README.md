# MQST-DEMO
MQST（Mobile Quick Simple To Thinkphp）是基于THINKPHP3.2框架之上的一个移动端架构解决方案，可流畅运行于几乎市面上所有的手机浏览器，亦可内嵌于APP中，对于需要频繁更新功能活动的APP来说也是个不错的选择。

## 开发环境
1、将配置DOMAIN_PATH的值改成你部署的项目域名或IP；<br>
2、将项目放置到网站根目录即可访问（该项目可直接使用，在IndexController里面直接添加你的代码即可）；<br>
3、建议使用phpstorm作为本项目的开发工具；<br>
4、如果配置MODULE_COMPRESSION_MODE=1的话，则加载的是混淆压缩版的min.js与min.css文件，否则直接加载源文件；<br>

## 关于如何使用phpstorm实现自动压缩JS与CSS文件
### 安装java
下载地址：https://www.java.com/zh_CN/<br>
安装教程参考：http://jingyan.baidu.com/article/f96699bb8b38e0894e3c1bef.html

### YUI Compressor
下载地址: https://github.com/yui/yuicompressor/releases/download/v2.4.8/yuicompressor-2.4.8.zip<br>
设置 File Watchers，打开 File -> Settings -> Tools -> File Watchers 中添加 YUI Compressor CSS 和 YUI Compressor JS<br>
（1）添加 YUI Compressor CSS<br>
在 Edit Watcher 窗口中，在 Program 位置参数设置为 [JAVA安装位置中javaw文件位于的路径]\javaw.exe，在 Arguments 位置参数设置为 -jar [yuicompressor文件位置的路径]\yuicompressor-2.4.8.jar --type css --charset UTF-8 $FileName$ -o $FileNameWithoutExtension$.min.css<br>
（2）添加 YUI Compressor JS<br>
在 Edit Watcher 窗口中，在 Program 位置参数设置为 [JAVA安装位置中javaw文件位于的路径]\javaw.exe，在 Arguments 位置参数设置为 -jar [yuicompressor文件位置的路径]\yuicompressor-2.4.8.jar --type js --charset UTF-8 $FileName$ -o $FileNameWithoutExtension$.min.js<br>

例如（我的配置）：<br>
YUI Compressor CSS<br>
Program:    C:\Program Files (x86)\Java\jre1.8.0_121\bin\javaw.exe<br>
Arguments:  -jar D:\deploy\lib\yuicompressor-2.4.8.jar --type css --charset UTF-8 $FileName$ -o $FileNameWithoutExtension$.min.css<br>

YUI Compressor JS<br>
Program:    C:\Program Files (x86)\Java\jre1.8.0_121\bin\javaw.exe<br>
Arguments:  -jar D:\deploy\lib\yuicompressor-2.4.8.jar --type js --charset UTF-8 $FileName$ -o $FileNameWithoutExtension$.min.js<br>

配置完成，尝试改变下js文件或css文件内容，若有新的min.js生成或min.css生成就证明配置成功啦~！

## 文件结构说明
Application<br>
  ├ Common<br>
  │   └ View<br>
  │       └  Sq<br>
  │           ├ base.tpl.html<br>
  │           │  （基础模版）<br>
  │           ├ footer.tpl.html<br>
  │           │  （底部模版：需要在页面底部引入的文件可以添加在这里）<br>
  │           ├ header.tpl.html<br>
  │           │  （头部模版：需要在页面头部引入的文件或meta可以添加在这里）<br>
  │           └ js_var.tpl.html<br>
  │               （常量传递模版：用于将PHP中的模版常量传递至JS变量）<br>
  └ Sq<br>
     ├ Common<br>
     │    ├ BaseController.class.php<br>
     │    │  （基控制器）<br>
     │    └ function.php<br>
     │        （公共函数库）<br>
     ├ Conf<br>
     │   ├ config.php<br>
     │   │  （主配置文件）<br>
     │   ├ db.php<br>
     │   │  （发布版数据库配置文件）<br>
     │   ├ sq_config.php<br>
     │   │  （发布版配置文件）<br>
     │   ├ test_db.php<br>
     │   │  （测试版数据库配置文件）<br>
     │   └ test_sq_config.php<br>
     │       （测试版配置文件）<br>
     ├ Controller<br>
     │   ├ CommonController.class.php<br>
     │   │  （公共控制器）<br>
     │   ├ IndexController.class.php<br>
     │   │  （首页控制器）<br>
     │   ├ DemoController.class.php<br>
     │   │  （Demo控制器）<br>
     │   ├ LoginController.class.php<br>
     │   │  （登录控制器）<br>
     │   └ AddressController.class.php<br>
     │       （选择地址控制器）<br>
     └ View<br>
          ├ Public<br>
          │  （公共视图模版文件目录）<br>
          ├ Index<br>
          │  （首页视图模版文件目录）<br>
          ├ Demo<br>
          │  （Demo视图模版文件目录）<br>
          ├ Login<br>
          │  （登录视图模版文件目录）<br>
          └ Address<br>
              （选择地址视图模版文件目录）<br>
Public<br>
  ├ css<br>
  │ ├ mqst.css<br>
  │ │  （全局通用定义样式）<br>
  │ └ module.css<br>
  │     （页面自定义样式）<br>
  ├ js<br>
  │ ├ config.js<br>
  │ │  （头部预加载js配置文件）<br>
  │ ├ library.js<br>
  │ │  （全局时间库文件）<br>
  │ ├ mqst.js<br>
  │ │  （全局通用函数库文件）<br>
  │ └ module.js<br>
  │     （页面自定义事件文件）<br>
  ├ images<br>
  │ （资源图片目录）<br>
  ├ ui<br>
  │ （核心UI库目录）<br>
  ├ aes<br>
  │ （aes加密插件目录）<br>
  ├ velocity<br>
  │ （velocity动画库目录）<br>
  └ zepto<br>
     （zepto移动端开发库目录）<br>

## 讨论
![](https://github.com/sq233/MQST-DEMO/raw/master/Public/images/public/qq_group_qr.jpg "技术交流群")  


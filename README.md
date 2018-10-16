# MQST-DEMO
MQST（Mobile Quick Simple To Thinkphp）是基于THINKPHP3.2框架之上的一个移动端架构解决方案，可流畅运行于几乎市面上所有的手机浏览器，亦可内嵌于APP中，对于需要频繁更新功能活动的APP来说也是个不错的选择。

## 开发环境
1、将配置DOMAIN_PATH的值改成你部署的项目域名或IP<br>
2、将项目放置到网站根目录即可访问<br>
3、建议使用phpstorm作为本项目的开发工具<br>
4、如果配置MODULE_COMPRESSION_MODE设置为1的话，则使用的是混淆压缩版的min.js与min.css文件，否则直接使用源文件<br>

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

## 讨论
![](https://github.com/sq233/MQST-DEMO/raw/master/Public/images/public/qq_group_qr.jpg "技术交流群")  


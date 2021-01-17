# cordova-template

快速打包web页面到移动端app

## 诞生背景

本仓库诞生的目的是解决从web网站搬到到移动端app问题,可打包android和ios,且操作简单。  
本仓库仅演示如何打包android，打包ios需要mac电脑和iphone，需要打包ios的同学请自行研究

## cordova 移动端原生功能插件

[Cordova插件](https://cordova.axuer.com/plugins/)  
[插件API](https://cordova.axuer.com/docs/zh-cn/latest/)

## 操作说明

### 安装cordova cli

```MAC OSX和linux```

```shell
sudo npm install -g cordova@9.0.0
```

```window```

```shell
npm install -g cordova@9.0.0
```

### 创建cordova工程

```shell
cordova create template com.template.app template
```

你可以把上面那条命令中所有的template换成你想要的名字
执行完后会在当前目录下生成template文件夹

### 搭建android开发环境

1. 安装JAVA SDK  
需要下载和安装1.8及之后的版本: ```https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html```，这里使用的是jdk-8u271-windows-x64.exe  
安装后设置环境变量,如何格式仅供参考,应根据自己的安装目录设置对应的环境变量地址  
JAVA_HOME  C:\Program Files\Java\jdk1.8.0_191  
CLASSPATH  .;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar  
在Path中增加 %JAVA_HOME%\jre\bin  和 %JAVA_HOME%\bin  

2. 安装android SDK  
访问网址  ```https://developer.android.google.cn/studio/  ```
不要下载android studio ，找到下方的“仅限命令行工具”，下载器其中的 commandlinetools-win-6858069_latest.zip，这个文件名可能会随时间更新，找到规律即可。  
下载之后将内容加压到D:\Android\Android-SDK目录，其实就一个tools文件夹，bin下sdkmanager.bat文件用户安装SDK  
设置环境变量，增加ANDROID_HOME，内容为D:\Android\Android-SDK，在Path中增加%ANDROID_HOME%\tools\bin和%ANDROID_HOME%\tools

3. 安装gradle  
从```https://services.gradle.org/distributions/gradle-4.1-bin.zip```，下载zip文件，解压到C:\Gradle\gradle-4.1，然后将C:\Gradle\gradle-4.1\bin加入到Path环境变量  

4. 检查安卓开发依赖

```shell
cordova requirements
```

如显示类似如下，说明安卓开发环境搭建成功：  
Java JDK: installed 1.8.0
Android SDK: installed true
Android target: installed android-28,android-27,android-26
Gradle: installed D:\program\gradle-4.10.3\bin\gradle

搭建安卓开发环境有些麻烦，如遇到问题，可自行百度解决

### 创建android项目  

```shell
cd template
cordova platform add android
```

### 运行测试版app

```shell
cd ..
npm run runAndroid
```

### 打包测试版

```shell
npm run build
```

如显示类似如下的路径，说明打包成功： ```D:\my_site\github\cordova-template\template\platforms\android\app\build\outputs\apk\debug\app-debug.apk```
如需打正式包，需要运行签名工具对app进行签名，有兴趣的同学自行百度

## webview在app端的应用案例

相应的页面截图在当前目录的webview文件夹下

```天翼生活（所有页面都是webview）```  
```个人所得税（所有页面都是webview）```  
```支付宝会员页面```  
```天猫超市页面```  
```天猫国际页面```  
```阿里健康页面```  
```淘宝心选页面```  
```拼多多首页上半部分的图标导航点进行的页面基本都是webview```  
```拼多多省钱月卡页面```  
```钉盘与文件页面```  
```招商银行资讯页面```  
```招商银行财富页面```  
```招商银行我的页面```  
```美团会员页面```  
```美团月付页面```  
```微信看一看页面```  
```中国移动底部导航的前四个板块```  
[查看详情](./webview/main.md)

## cordova官网

[https://cordova.apache.org/](https://cordova.apache.org/)

## cordova中文网

[https://cordova.axuer.com/](https://cordova.axuer.com/)

## 关联链接

[快速打包web页面到电脑应用程序](https://github.com/zhoushoujian/electron-template)  

[express + mongodb + redis + jwt + typescript项目模板](https://github.com/zhoushoujian/typescript-express-templates)  

[React + Redux + typescript项目模板](https://github.com/zhoushoujian/typescript-react-templates)  

## License

[MIT](./LICENSE)

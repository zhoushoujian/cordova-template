# cordova-template

快速打包 web 页面到移动端 app

## 诞生背景

本仓库诞生的目的是解决从 web 网站搬到到移动端 app 问题,可打包 android 和 ios,且操作简单。  
本仓库仅演示如何打包 android，打包 ios 需要 mac 电脑和 iphone，需要打包 ios 的同学请自行研究

## cordova 移动端原生功能插件

[Cordova 插件](https://cordova.axuer.com/plugins/)  
[插件 API](https://cordova.axuer.com/docs/zh-cn/latest/)

## 操作说明

### 安装 cordova cli

`MAC OSX和linux`

```shell
sudo npm install -g cordova
```

`window`

```shell
npm install -g cordova
```

### 创建 cordova 工程

```shell
cordova create template com.template.app template
```

你可以把上面那条命令中所有的 template 换成你想要的名字
执行完后会在当前目录下生成 template 文件夹

### 搭建 android 开发环境

1. 安装 JAVA SDK  
   需要下载和安装 1.8 及之后的版本: `https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html`，这里使用的是 jdk-8u271-windows-x64.exe  
   安装后设置环境变量,如何格式仅供参考,应根据自己的安装目录设置对应的环境变量地址  
   JAVA_HOME C:\Program Files\Java\jdk1.8.0_191  
   CLASSPATH .;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar  
   在 Path 中增加 %JAVA_HOME%\jre\bin 和 %JAVA_HOME%\bin

2. 安装 android SDK  
   访问网址 `https://developer.android.google.cn/studio/`
   不要下载 android studio ，找到下方的“仅限命令行工具”，下载器其中的 commandlinetools-win-6858069_latest.zip，这个文件名可能会随时间更新，找到规律即可。  
   下载之后将内容加压到 D:\Android\Android-SDK 目录，其实就一个 tools 文件夹，bin 下 sdkmanager.bat 文件用户安装 SDK  
   设置环境变量，增加 ANDROID_HOME，内容为 D:\Android\Android-SDK，在 Path 中增加%ANDROID_HOME%\tools\bin 和%ANDROID_HOME%\tools

3. 安装 gradle  
   从`https://services.gradle.org/distributions/gradle-4.1-bin.zip`，下载 zip 文件，解压到 C:\Gradle\gradle-4.1，然后将 C:\Gradle\gradle-4.1\bin 加入到 Path 环境变量

4. 检查安卓开发依赖

```shell
cd template
cordova requirements
```

如显示类似如下，说明安卓开发环境搭建成功：  
Java JDK: installed 1.8.0
Android SDK: installed true
Android target: installed android-28,android-27,android-26
Gradle: installed D:\program\gradle-4.10.3\bin\gradle

搭建安卓开发环境有些麻烦，如遇到问题，可自行百度解决

### 创建 android 项目

```shell
cordova platform add android
```

### 打包测试版

```shell
cd ..
npm run build
```

如显示类似如下的路径，说明打包成功： `D:\my_site\github\cordova-template\template\platforms\android\app\build\outputs\apk\debug\app-debug.apk`
如需打正式包，需要运行签名工具对 app 进行签名，有兴趣的同学自行百度

### 使用

把你的 web 静态文件放到 template 目录下的 www 目录下，入口文件为 index.html

## webview 在 app 端的应用案例

相应的页面截图在当前目录的 webview 文件夹下

`天翼生活（所有页面都是webview）`  
`个人所得税（所有页面都是webview）`  
`支付宝会员页面`  
`天猫超市页面`  
`天猫国际页面`  
`阿里健康页面`  
`淘宝心选页面`  
`拼多多首页上半部分的图标导航点进行的页面基本都是webview`  
`拼多多省钱月卡页面`  
`钉盘与文件页面`  
`招商银行资讯页面`  
`招商银行财富页面`  
`招商银行我的页面`  
`美团会员页面`  
`美团月付页面`  
`微信看一看页面`  
`中国移动底部导航的前四个板块`  
[查看详情](./webview/main.md)

## cordova 官网

[https://cordova.apache.org/](https://cordova.apache.org/)

## cordova 中文网

[https://cordova.axuer.com/](https://cordova.axuer.com/)

## 关联链接

[快速打包 web 页面到电脑应用程序](https://github.com/zhoushoujian/electron-template)

[express + mongodb + redis + jwt + typescript 项目模板](https://github.com/zhoushoujian/typescript-express-templates)

[React + Redux + typescript 项目模板](https://github.com/zhoushoujian/typescript-react-templates)

[nextjs + redux + express + less 服务端渲染项目模板](https://github.com/zhoushoujian/nextjs)

[taro 小程序项目模板](https://github.com/zhoushoujian/taro)

## License

[MIT](./LICENSE)

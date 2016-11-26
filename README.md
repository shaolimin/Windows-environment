# Windows-environment
windows下的react-native 环境搭建
------------------------------------------
### 一、准备工作
  安装jdk，配置jdk的环境变量
  > 
  配置android开发环境，配置sdk的环境，这里的sdk必须有23版本
  > 
  安装genymotion，当然这里也可以使用真机调试，我推荐蓝叠>
  > 
  安装git
  > 
  安装node.js(版本6.0以上) 并配置环境变量

### 二、react native环境搭建

我在e盘下创建一个reactnative目录，用来存放创建的工程，进入该目录，执行如下命令：
 npm install -g react-native-cli
 react-native init firstProject
npm install -g react-native-cli    会安装react native需要的相关组件。
react-native init firstProject        会创建一个叫做firstProject的工程 
这里一定要保持网络畅通，最好可以翻墙，如果不行，可以运行如下命令设置npm国内的代理：
     npm config set disturl https://npm.taobao.org/dist
完成之后会在该目录下新创建一个firstProject的工程： 
这里写图片描述
运行android应用

至此，firstProject工程已经创建好了，进入该工程目录，执行如下命令，运行该工程：

         react-native start
     react-native run-android
之后在执行
     adb reverse tcp:8081 tcp:8081
### 三、注意
需要注意的是，在运行该命令的之前必须打开模拟器，或者连上真机调试。千万切记：在正式运之前，最好另外打开一个窗口，还要通过react-native start来开启服务如下： 
这里写图片描述
这里写图片描述 
服务开启完成，可以先查看下该条服务是否可用，打开谷歌浏览器，按照提示输入如下链接： 
http://localhost:8081/index.android.bundle?platform=android 
此时可能会遇到如下错误： 
这里写图片描述 
解决：
点击手机上的menu按钮，调出如下图的样子
                            

选择Dev setting 
                             
 在选择debug server host
                             
填写ip地址
(1)当前网络的ip
(2)127.0.0.1:8081
(3)10.0.0.1:8081
选择reload js        

如果一直出现红色屏幕，使用
adb reverse tcp:8081 tcp:8081
               
最终的效果如下： 
这里写图片描述
真机无线调试

首先通过usb连接电脑，打开两个终端窗口，分别执行如下命令：
     react-native start  #开启服务
     react-native run-android #编译并运行apk
此时，如果同样遇到unable to download js bundle这样的错误，拔掉usb线，注意：手机和PC必须要在同一局域网下。
点击手机的menu按钮，或者摇一摇手机，选择dev setting
选择”debug server host & port for device”
输入：PC的ip地址：端口号 ex：192.168.0.102:8081
点击menu，或者摇一摇手机，点击reload js即可








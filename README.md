# Windows-environment
windows下的react-native 环境搭建
------------------------------------------
### 一、准备工作
  > 
  (1)安装jdk，配置jdk的环境变量
  > 
  (2)配置android开发环境，配置sdk的环境，这里的sdk必须有23版本
  > 
  (3)安装genymotion，当然这里也可以使用真机调试，我推荐蓝叠
  > 
  (4)安装git
  > 
  (5)安装node.js(版本6.0以上) 并配置环境变量

### 二、react native环境搭建

我在e盘下创建一个reactnative目录，用来存放创建的工程，进入该目录，执行如下命令：
> 
 npm install -g react-native-cli   (会安装react native需要的相关组件)。
 > 
 react-native init firstProject     (会创建一个叫做firstProject的工程) 
 >      
这里一定要保持网络畅通，最好可以翻墙，如果不行，可以运行如下命令设置npm国内的代理：
> 
 npm config set disturl https://npm.taobao.org/dist
> 

### 三、运行android应用

至此，firstProject工程已经创建好了，进入该工程目录，执行如下命令，运行该工程：
>
     react-native start
>
     react-native run-android
之后在执行
     adb reverse tcp:8081 tcp:8081
### 四、注意
摇晃手机弹出界面，选择Dev setting
>
在选择debug server host
>                             
填写ip地址
(1)当前网络的ip
>
选择reload js        
>
如果一直出现红色屏幕，使用
>
adb reverse tcp:8081 tcp:8081








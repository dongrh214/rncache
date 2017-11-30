进入项目根目录后，使用 run-ios 指令启动该iOS APP：

react-native run-ios 
对于版本高于0.45的创建项目，也许你会看到如下错误：

Error:   
Build failed: 
Unpacking /Users/zjy/.rncache/boost_1_63_0.tar.gz...  
Print: Entry, ":CFBundleIdentifier", Does Not Exist 
对应的直接点开.xcodeproj 运行相关的错误信息 

1、降级版本方案

下载安装node依赖模块时的资源缺失问题，目前最新的0.45及以上版本需要下载boost库，该库过大，导致下载出问题

解决方案有两种，如果不追求新版本新特性，可以降低创建项目的版本，使用 --version 指令明确设置项目版本：

react-native init MyApp --version 0.44.3 

2、替换资源文件方案
下载项目内四个相关文件放到项目根目录下的 .rncache 目录下，进行替换

下载后替换：

command+shift 输入.rncache ,打开.rncache目录，拖入以上四个文件

然后删除第三方库文件，在 node_modules/react-native/third-party/ 目录下：
rm -rf node_modules/react-native/third-part 
再次执行启动程序：

react-native run-ios 

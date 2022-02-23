# PPT Stabilizer

## 软件介绍

### 介绍

PPT Stabilizer 是由WZSJC2022 在2022年2月19日开发的，并在2022年2月21日发布了Release V0.1.0版本。这款工具是一个简易的PPT播放器。键盘自定义延迟播放PPT。

很遗憾的是这个软件原计划是由WIN32.DLL接口开发的，但是作者表示真的看不懂，所以并不能使用.pptx格式的方式加载你的幻灯片文件，而是使用了加载图片文件。这让幻灯片动画的效果不能实现。

### 推荐配置以及依赖库

磁盘空间：200MB以上
运行内存：1GB以上
系统：Windows10/11
依赖：fastJSON(程序内置), JAVASE 8

## 功能以及自定义配置

通过options.json配置文件对文件的变量进行修改

### options.json(V0.1.1-V0.1.2)

{
  "imgFolderName": "inventory",				//设置图片文件夹名称，必须和%run.jar同级目录
  "isUndecorated": false,							//是否关闭窗口装饰器（建议设置为true，否则加载不完全）
  "preferredSystemResolution": false,		//是否使用系统分辨率（建议设置为true，否则非全屏显示）
  "WINDOW_W": 1280,								//当isUndecorated=false时，设置窗口宽度
  "WINDOW_H": 720,								//当isUndecorated=false时，设置窗口高度
  "LONG_PRESS": 500,								//设置按键需要多少延迟
  "KEY_NEXT": 40,										//设置播放下一页的键盘输入
  "KEY_CONTROL_PANEL": 80,				//设置打开控制面板的键盘输入
  "isShow_KEY_FORWARD": true,				//设置按键-下一页是否在控制栏中显示
  "isShow_KEY_PREVIOUS": true,				//设置按键-前一页是否在控制栏中显示
  "isShow_KEY_FIRST": true,						//设置按键-第一页是否在控制栏中显示
  "isShow_KEY_LAST": true,							//设置按键-最后一页是否在控制栏中显示
  "isShow_KEY_TIMER": true,						//设置按键-计时器是否在控制栏中显示
  "isShow_KEY_EXIT": true							//设置按键-退出是否在控制栏中显示
}

### options.json(V0.1.0)

{
  "imgFolderName": "inventory",				//设置图片文件夹名称，必须和%run.jar同级目录
  "isUndecorated": false,							//是否关闭窗口装饰器（建议设置为true，否则加载不完全）
  "preferredSystemResolution": false,		//是否使用系统分辨率（建议设置为true，否则非全屏显示）
  "WINDOW_W": 1280,								//当isUndecorated=false时，设置窗口宽度
  "WINDOW_H": 720,								//当isUndecorated=false时，设置窗口高度
  "LONG_PRESS": 500								//设置按键需要多少延迟
}

## 常见问题

### 如果遇到问题无法自行解决的请及时联系作者

QQ：3477001941

### 1.双击启动程序闪退

这种情况通常是因为路径不规范造成的，比如路径下有中文，有空格，或者是%run.jar文件被改名
其次可以尝试使用cmd终端 输入 java -jar C:\这里替换成你当前文件夹的路径\%run.jar，这样可以显示具体是哪一步报错了，如果依旧报错，请联系作者

## 开发者

本程序暂时不开源
本作品采用知识共享署名-非商业性使用-相同方式共享 4.0 国际许可协议进行许可。
遵循以下协议： https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh
转载务必附上作者及原贴，禁止商业用途的转载和发布
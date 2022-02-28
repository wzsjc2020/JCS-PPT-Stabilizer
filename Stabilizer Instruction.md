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

### options.json(V1.0.0)

基本与之前一致
{
  "imgFolderName": "inventory",						//设置图片文件夹名称，必须和Stabilizer.jar同级目录
  "hotKeys": [
    {
      "LONG_PRESS": 500,								////设置按键需要多少延迟（默认500毫秒）
      "KEY_NEXT": 40,										//设置播放下一页的键盘输入（默认下键）
      "KEY_CONTROL_PANEL": 80					//设置打开控制面板的键盘输入(默认P键)
    }
  ],
  "display": [
    {
      "isUndecorated": false,								//是否关闭窗口装饰器（全屏建议设置为true，否则加载不完全）
      "WINDOW_W": 1920,								//设置窗口宽度
      "WINDOW_H": 1080									//设置窗口高度	
    }
  ],
  "functionKeys": [
    {
      "x": 20,														//设置功能键图标在屏幕上的初始X值
      "y": 50,														//设置功能键图标在屏幕上的初始Y值
      "width": 64,												//设置功能键图标的宽度
      "height": 64,												//设置功能键图标的高度
      "h_gap": 20,												//设置功能键图标之间的水平间距
      "v_gap": 20,												//设置功能键图标之间的竖直间距
      "isHorizontal": false									//功能键图标是否水平排列
    },
    {
      "keyName": "next",									//这里我们用next按键作为演示*
      "rank": 2,											//排列的顺序，这里的 2表示 排列在第三位（0为第一位，-1不加载）
      "isShow": "true",										//是否显示显示图标
      "imagePath": "icon/next.png"					//文件的的路径，为了方便用户自定义图标，详见常见问题4
    },

### options.json(V0.1.1-V0.1.3)

{
  "imgFolderName": "inventory",				//设置图片文件夹名称，必须和Stabilizer.jar同级目录
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

这种情况通常是因为路径不规范造成的，比如路径下有中文，有空格
其次可以尝试使用cmd终端 输入 java -jar C:\这里替换成你当前文件夹的路径\Stabilizer.jar，这样可以显示具体是哪一步报错了，如果依旧报错，请联系作者

### 2.点击功能按键时，程序反应延迟或没有反应

这种情况作者经过测试，发现并非程序监听器的问题，而是鼠标不兼容。请尝试更换一个鼠标或使用键盘自带的触摸板进行测试，如果问题解决，大概率说明您的鼠标对JAVA SWING监听器的兼容不是很好。

### 3.图片加载顺序不对如何解决

这种情况经过测试确实存在，这是因为文件命名不规范导致的，目前作者尚未对此做出优化
可以通过  reNamer 软件对文件名统一改名，比如一号改名 01.jpg ；十号文件命名成10.jpg就不会出现以上问题
通过office导出的图片确实存在该问题，一定要记得改名，也请提前测试一下是否会出现排序混乱的情况发生

### 4.如何自定义功能键图标

Stabilizer自带了一套系统内置的图标，同时提供了用户自定义图标的功能
1.第一步查看内置图标的位置，V1.0.0可以直接在 options.json中查看图标的内部路径
2.在Stabilizer.json的同级根目录新建一个路径为  resources\pptStabilizer\icon 的文件夹
3.把贴图的名字改名成与内置库中相同的文件名，即可正常显示

## 开发者

本程序暂时不开源
本作品采用知识共享署名-非商业性使用-相同方式共享 4.0 国际许可协议进行许可。
遵循以下协议： https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh
转载务必附上作者及原贴，禁止商业用途的转载和发布
## Release_V0.1.0（2022.2.21）

1.第一个正式版发布

## Release_V0.1.1（2022.2.22）

1.修复了#20220221b
2.现在可以使用KEY_NEXT，KEY_CONTROL_PANEL自定义按键

```
"KEY_NEXT": 40,						//下一张PPT（默认下键）
"KEY_CONTROL_PANEL": 80,			//打开控制面板（默认P键）
按键编码请查询 KeyEvent.java
```

3.优化了IOToolkit.readJsonFile() 调用过多的问题
4.优化了jar路径的判断，现在不需要使用%作为jar文件的开头，但依旧路径中不得包含中文以及空格
5.修复了#20220222a
6.新增了5个功能按键，可以在options.json中自定义是否开启

```
"isShow_KEY_FORWARD": false,		//是否显示下一页按键
"isShow_KEY_PREVIOUS": true,		//是否显示前一页按键
"isShow_KEY_FIRST": true,			//是否显示回到第一页按键
"isShow_KEY_LAST": false,			//是否显示跳转到最后一页按键
"isShow_KEY_EXIT": true				//是否显示退出按键
```

## Release_V0.1.2（2022.2.23）

1.修复了#20220222b严重错误
2.添加了自定义解析图片工具ImageToolkit.autoSelectAbsoluteImagePath()
用户可以在根目录路径下重绘部分开放此功能的图片

```
autoSelectAbsoluteImagePath(String imagePathFromConstant)
```

## Release_V0.1.3（2022.2.23）

1.修复了自定义解析图片工具ImageToolkit.autoSelectAbsoluteImagePath()
2.修复了#20220223a
3.本版本为最终版本，不再提供更新

## Express Edition V1.0.0 (2022.2.27)

1.重新架构了程序，其实际效果与V0.1.3并没有明显区别
2.删除了自V0.0.1版本以来的preferredSystemResolution设置，现在不再通过系统分辨率来设置画面大小

```
"preferredSystemResolution": false,			//已被移除
```

3.现在可以通过设置isHorizontal设置功能按键的竖直或横向排列

```
"functionKeys": [
  {
    "x": 20,							//图标初始X位置
    "y": 50,							//图标初始Y位置
    "width": 64,						//图标的宽度
    "height": 64,						//图标的长度
    "h_gap": 20,						//图标间的横向距离
    "v_gap": 20,						//图标间的纵向距离
    "isHorizontal": false				//是否水平排列
  },
```

4.现在可以加强自定义图标路径，可以设置图标排列位置，以及图标是否在界面中显示

```
{
  "keyName": "next",						//功能键名称
  "rank": 2,								//排列顺序，如果不想显示在界面请设置为-1
  "isShow": "true",							//是否显示
  "imagePath": "icon/next.png"				//图标的路径
},
```

5.修复了闪屏的问题



## BUGS

### #20220221a UN

程序绝对路径下有中文名或空格时导致程序无法运行

### #20220221b

projIcon无法正常加载

### #20220222a

CasinoCoreConstant.ERROR_INFO错误贴图未能正常加载

### #20220222b

V0.1.1 长按键盘任意按键不放，随后轻点下键，获取时间间隔数据有误，导致直接播放下一页

### #20220223a

V0.1.2 内部类封装图片无法显示

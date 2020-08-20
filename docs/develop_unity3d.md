## 简介
  HoloCatchLightPlugin提供简单高效的体积视频解码，开发者可以利用HoloCatchLightPlugin在Unity3d中进行体积视频的解码预览与二次开发，

## 主要特性

* 提供录播和实时直播的高性能解码能力
* 可在编辑器模式预览
* 全平台
* 可通过Timeline控制（Pro版本）

## 支持设备

* Window
* Mac
* IOS
* Android
* Hololens

## 开发环境要求
    unity2018.4以上，建议unity2019.3及以上

## 文件目录
    ├─Prometh 插件主要部分
    │  ├─Editor
    │  │      MeshPlayerPluginEditor.cs 编辑器脚本，提供编辑器模式预览等功能
    │  │
    │  ├─Plugins 各个平台的库
    │  │  ├─arm64-v8a 对应安卓64位平台
    │  │  ├─armeabi-a7v 对应安卓32位平台
    │  │  ├─ios 对应ios平台
    │  │  ├─Mac 对应Mac平台
    │  │  ├─UWP 对应Hololens平台(UWP平台需要切换至对应平台，然后从压缩包中解压出目录中的插件)
    │  │  └─x86_64 对应安卓64位平台
    │  │
    │  ├─Prefabs
    │  │  │  PromethCube.prefab 用来快速使用的预制体
    │  │  │
    │  │  └─Material
    │  │          Logo.png
    │  │          MatPrometh.mat 预制体对应材质，需要使用Unlight
    │  │
    │  ├─Scripts
    │  │      MeshPlayerPlugin.cs 插件C#主要逻辑部分
    │  │      MeshReader.cs C#部分与底层API的中间层，封装成MeshData数据
    │  │      ReaderAPI.cs 调用底层API的部分
    │  │
    │  ├─Scenes
    │  │      PromethLocal.unity 基本功能场景
    │  └─StreamingAssets 首先要将这个文件夹移到根目录，视频文件要放在这里


## 快速入门
首先将Prometh/StreamingAssets文件夹放到Assets根目录
您可以直接运行Scene里面的Demo场景来快速使用，或者新建场景自行创建，首先将PromethCube拖进场景，将组件中的SourceType选择为PLAYBACK，SourcePath填入StreamingAssets文件夹下的路径，记得加上.mp4后缀，在StreamingAssets下文路径要勾选InStreamingAssets属性，编辑器下可以点击PreviewFrame进度条进行预览，SourceDurationSec，是当前模型的总时长，SpeedRatio为模型的播放速度。

## API控制
MeshPlayerPlugin提供出一些接口可以对视频播放进行控制
* MeshPlayerPlugin.OpenSource(string str)  // 打开文件，参数为地址，StreamingAssets文件夹下的路径，否则为绝对路径
* MeshPlayerPlugin.Play()  // 播放
* MeshPlayerPlugin.Pause()  // 暂停
* MeshPlayerPlugin.GotoSecond(float sec)  // 跳到多少秒
* MeshPlayerPlugin.SpeedRatio //控制速度，播放前生效

## 演示视频
[![Unity3D Demo Video](imgs/07.png)](https://www.bilibili.com/video/BV1Dt4y1C7Qs)

* 您有什么疑问或者需求请联系技术支持: busiyg@163.com

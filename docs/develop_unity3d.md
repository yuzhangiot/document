# Unity3D 插件使用教程

## 简介

    unityMeshPlayer提供简单高效的体积视频解码，开发者可以利用unityMeshPlayer在Unity3d中进行体积视频的解码预览与二次开发，

## 主要特性

* 提供录播和实时直播的高性能解码能力
* 可在编辑器模式预览
* 全平台
* 可通过Timeline控制

## 支持设备

* Window
* Mac
* IOS
* Android

## 开发环境要求
    unity2018.4以上，建议unity2019.3及以上

## 文件目录
    ├─DemoScene 示例场景包含模型预览的视角交互，材质切换功能
    │  ├─Material
    │  │      Meshplayer.mat
    │  │      MyShader.shader
    │  │      NormalMaterial.mat
    │  │
    │  ├─Scene
    │  │      DemoScene.unity
    │  │
    │  ├─Scripts
    │  │      MeshPlayerController.cs
    │  │      ModelViewController.cs
    │  │      UIManager.cs
    │  │
    │  └─Texture
    │          circle_128.png
    │
    ├─Prometh 插件主要部分
    │  ├─Editor
    │  │      MeshPlayerPluginEditor.cs 编辑器脚本，提供编辑器模式预览等功能
    │  │
    │  ├─Plugins 各个平台的库
    │  │  ├─arm64-v8a 对应安卓64位平台
    │  │  ├─armeabi-a7v 对应安卓32位平台
    |  │  ├─ios 对应ios平台
    │  │  ├─Mac 对应Mac平台
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
    │  └─TimeLine 通过TimeLine去控制模型播放的实现部分
    │          PromethPlayableAsset.cs
    │          PromethPlayableAsset.cs.meta
    │          PromethPlayableBehaviour.cs
    │          PromethPlayableBehaviour.cs.meta
    │          Timeline.playable
    │          Timeline.playable.meta
    │          TrackPrometh.cs
    │          TrackPrometh.cs.meta
    │
    ├─Scenes
    │      PromethLocal.unity 基本功能场景
    │      TimeLineDemo.unity 通过TimeLine控制的案例场景
    │
    └─StreamingAssets 在Unity工程中的视频文件要放在这里进行播放

## 快速入门
将PromethCube拖进场景，将组件中的SourceType选择为PLAYBACK，SourcePAth填入StreamingAssets文件夹下的路径，记得加上后缀，在StreamingAssets下文路径要勾选InStreamingAssets属性，编辑器下可以点击PreviewFrame进度条进行预览，SourceDurationSec，是当前模型的总时长，SpeedRatio为模型的播放速度。

## API控制
MeshPlayerPlugin暴露出一些接口可以对视频播放进行控制
* MeshPlayerPlugin.OpenSource(string str)  // 打开文件，参数为地址，StreamingAssets文件夹下的路径，否则为绝对路径
* MeshPlayerPlugin.Play()  // 播放
* MeshPlayerPlugin.Pause()  // 暂停
* MeshPlayerPlugin.SetMaterial(Material mat)  // 切换材质
* MeshPlayerPlugin.GotoSecond(float sec)  // 跳到多少秒
* MeshPlayerPlugin.SpeedRatio //控制速度，播放前生效

## 演示视频
[![Unity3D Demo Video](imgs/07.png)](https://www.bilibili.com/video/BV1Dt4y1C7Qs)

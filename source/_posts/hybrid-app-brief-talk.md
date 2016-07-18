title: 浅谈Hybrid App
date: 2016-07-18 11:44:06
tags:
  - Hybrid
  - H5
  - 混合开发
categories:
  - App
---

# 浅谈Hybrid App开发 
> 我们常说的：在Android、iOS上的用H5来做界面

我们把档次稍微提高一下：
> 今天和大家分享的是** Hybrid App 的开发**

**Hybrid App开发**

* 它不是手机网页开发、不是html、不是h5，但又都是
* 做这个需要懂iOS、Android，还要懂html、js、css
* 最麻烦的还是兼容性，主要的工作还是在web开发上
* 已是主流了
 
![](/blog/post_images/hybrid-app-brief-talk-01.png)

# 为什么要谈Hybrid App开发
* ## 我们现在的App就是Hybrid App
  > 所以我们做得比较简单
  
* ## 主流，基本上现在常用的App都是Hybrid App
  > AppStore、Instagram、微信(公众号、钱包)、支付宝（城市服务、电影、）、美团、滴滴、京东、汽车之家、联通手机营业厅……
  
* ## 快速迭代，在不更新APP的情况下，修改、新增功能
  > 例如：我们的新版首页，只要在服务器更新了，我的APP可以很快增加一个弱交互的模块；发现一些bug，也可以直接热修复
  
* ## 开发统一，不管是Android、iOS，甚至是WP都可以统一开发，减少各个平台功能不统一的问题
  > 1.原生开发专注于底层核心模块的开发、优化，封装好与web的交互接口。web实现功能模块后，所有端都无需重新开发
  
  > 2.例如：视频直播。原生开发专注与视频推流、视频播放、聊天功能的开发、优化，消息推送等，用web实现直播列表、直播创建等展示、数据编辑功能开发。相互之间定义好调用接口即可。
  
* ## 总结我们现在混合开发发现的问题，优化我们的App 
  > 我们可以做得更好


# 常见App开发模式

## Native App
> Native App，原生APP，一般依托于操作系统，有很强的交互，是一个完整的App，可拓展性强。需要用户下载安装使用。**原生开发人员数量众多，技术已成熟**。Android用Java语言，开发环境用android studio或Eclips等IDE；iOS用oc、swift，Mac+Xcode开发环境；WP用C#/C++，windows+Visual studio环境。

### 优点

> 1. 性能好，用户体验最贴近系统
> 2. 能够访问本地资源（通讯录，相册、存储空间……）
> 3. 能够实现大部分的功能

### 缺点：

> 1. 无法跨平台：Android和iOS都需要开发各自平台的版本——开发成本高；
> 2. 升级麻烦：每次升级都要下载安装包，Android还好，反正不需要审核，下载就下载吧，但iOS就麻烦了，发布每个版本还得经过App Store的审核，这导致第三个问题；
> 3. Android和iOS很难同步发布。


## Web App
> 基本上H5写出的App，不需要下载安装。类似于现在所说的轻应用。生存在浏览器中的应用，基本上可以说是触屏版的网页应用。但也有电脑网页版的Web App，例如微软的office 365，Gmail等。

### 优点
> 1. 无需升级、更新快
> 2. 同时跨多个平台、多个端
> 3. 用户使用方便

### 缺点
> 1. 体验较差、设计受限制诸多
> 2. 设计受限制诸多
> 2. 无法获取系统级别的通知，提醒，动效等等


## Hybrid App
> 半原生半Web的混合类App。需要下载安装，看上去类似Native App，部分是用WebView，访问的内容是Web。但**涉及到的技术成本、开发成本、学习成本比Web App高**，它综合了**Web App的开发速度和Native App的高性能体验**。

> 不管是Native还是Web，都具有各自的UI和布局能力、数据交互能力和脚本调用能力等。所以，**Hybrid App更是一种开发模式，如何有效混合使用是个很大的技巧**。

## 特性对比
> 
|   | Native | Hybrid | web |
| -- | -- | -- | -- |
| 用户体验 | 很好 | 好 | 一般 |
| 图像渲染 | 本地API | html、Canvas、css | 混合 |
| 性能 | 非常快 | 快 | 慢 |
| 跨平台成本 | 高 | 合理 | 低 |
| 碎片化 | **非常严重** | 严重 | 严重 |
| 版本维护 | 保守 | 低延时 | 开放 |
| 网络要求 | 支持离线 | 大部分依赖网络 | 完全依赖网络 |

<!--
## 技术特性对比
![技术特性](duibi.png)
-->


# Hybrid App误区

## 为了H5而Hybrid App

HTML5在Hybrid App模式中是一个最常被提起的概念。HTML确实强大，但HTML5处在目前的发展阶段，受到浏览器兼容性和手机硬件性能水平的影响，它所能提供的功能与Native仍然有很大差距。

要明确一款App采用Hybrid App模式的根本原因是什么。**作为一款App其最根本的功能是满足使用者的需求，而并不是服务某项新技术**。

## 忽略关键因素

谈到Hybrid App我们更多提及的是它有诸多优点，会被忽略的一些因素少被提起，**这些因素又恰恰经常是一个Web页面能否正常运行在App中的决定性因素**。

> 无论是iOS还是Android，最敏感的一个问题莫过于内存管理，而在Web开发则对这个问题没有过多注意。

在网络环境方面，App在Wifi、3G的切换，基站变化等诸多因素都会导致网络间歇性断开，但Web开发总是默认有一个稳定的网络环境,因此在对于不稳定网络环境问题的处理上也有所欠缺。

> **没有明确的对于低速网络或不稳定网络访问的处理，在很多情况下这些页面的用户体验是很差的。**

## 富交互导致体验差

1. 平台(Android/iOS/WP/PC)默认交互习惯不一致的体验。
2. 同样功能和Native界面存在的体验差距。
> 无论在Android还是iOS平台上，都有各自的一套交互习惯，包括视觉风格，界面切换，操作习惯等，与Web习惯完全不同。
> 
> 当然Web方式也可模拟Native的交互方式，但**这样的模拟首先提高了开发成本，有悖于最初的高效原则，从效果上看，也很难达到Native的流畅性**。

## 跨平台
1. 一次开发，跨平台运行是Web的优势，这也是很多App采用Hybrid模式的重要原因之一。但是**兼容性绝对是一个不容忽视的问题。**
2. 无论是机型、版本众多的Android，还是相对统一的iOS,不同版本之间的差异还是不容忽视的。

Hybrid App方案是一把双刃剑，一方面它平衡了Native App和Web页面的优缺点，一定程度上解决了迭代慢，版本依赖的问题，但另一个方面**过度依赖Hybrid方案会造成Web前端开发成本快速上升，甚至造成App整体体验下降，甚至造成功能缺失。**

## 注意
> 不要为了H5而Hybrid，控制好App中Native与Web的边界是重中之重。


# 常见的Hybrid App开发解决方案

## Cordova/PhoneGap
2010年将PhoneGap代码贡献给Apache软件基金（ASF），PhoneGap核心引擎成为新的开源项目Cordova。

提供Hybrid API，可由JavaScript直接调用诸如加速度、摄像头、指南针、GPS、联系人等系统级API，完整的API列表请访问PhoneGap API Reference。
侧重于JS与原生的交互，**开发简单，但性能差**，如触摸时反应不灵敏。

用户列表：[维基百科客户端](https://github.com/wikimedia/WikipediaMobile) [LinkedIn iPad客户端](https://mobile.linkedin.com/zh-cn) 

## Ionic Framework

我们现在正在用

## MUI和HTML5+ SDK

> 定位：最接近原生体验的移动App的UI框架 [mui产品概述](http://ask.dcloud.net.cn/docs/#http://ask.dcloud.net.cn/article/91)
> 
> 以iOS平台UI为基础，补充部分Android平台特有的UI控件

HTML5+ SDK
> 1. 使用HTML5+ SDK实现本地打包。
1. 通过原生代码扩展HTML5+ runtime的功能。
1. 在现有原生项目中使用HTML5+ SDK**替换原有的webview，以获得更强的web增强表现**。
>  [HTML5+ SDK 功能概述](http://ask.dcloud.net.cn/docs/#http://ask.dcloud.net.cn/article/104)

用户列表：360生活助手 [明道OA](https://itunes.apple.com/cn/app/id468630782) [会留学](https://itunes.apple.com/cn/app/hui-liu-xue-kou-dai-li-liu/id1044958285?mt=8)

## React Native

[React Native @ github](http://facebook.github.io/react-native/)

Facebook出品，初次学习成本很高，但优势是“Learn once, write anywhere”。React Native仍然不完善。iOS版本比较完善，Android版本还是实验性产品。

优势：
1. 实际上没有用到Webview，彻底摆脱了Webview让人不爽的交互和性能问题
2. 有较强的扩展性，这是因为Native端提供的是基本控件，JS可以自由组合使用
3. 可以直接使用Native原生的「牛逼」动画（在FB Group这个app里面，面板滑出带一点果冻弹动，面板基于某个点展开这种动画随处可见，这种动画用Native code来做小菜一碟，但是用Web来做就难上加难）。


# 我们怎么做

## 目标

1. 能够快速更新，但不需要更新App
2. 减少不同平台重复开发的工作量
3. 尽可能在UX上贴近原生
4. 用户无感知，用户不会感觉到就是打开一个网页

## 用户体验

1. 流畅性一定要好
2. 完美兼容Android4.0以上、iOS7.0以上系统
2. 不要出现这种情况
   * 网络不好的情况下完全空白的现实 ![空白](/blog/post_images/hybrid-app-brief-talk-02.jpg)
 * 404，502之类的不直观提示   ![502](/blog/post_images/hybrid-app-brief-talk-03.png)


## 缓存

> 1. 使用http请求头部的[If-Modified-Since](http://www.cnblogs.com/zh2000g/archive/2010/03/22/1692002.html)、[If-None-Match](http://baike.baidu.com/item/ETag)
> ；使用http响应头部的Last-Modify、Cache-Control
> 2. 重要的界面，App本身最好缓存一份，避免网络原因造成的界面空白
> 3. App端的缓存机制尽量按http响应头里参数来设置，除非用户强制刷新
> 4. 大的第三方js库、字体最好App本身就已经集成，不需要从网络下载
> 5. 对于一些不常变化的文件，可以集成在App内
<!--  6. 使用*suppressesIncrementalRendering:YES*  -->

## 这样做

1. 现阶段只针对交互较少的节目才考虑试用web实现，
1. 使用○转圈圈之类的加载动画代替进度条加载，这样会感觉更像原生
1. 将一些App本身的业务封装好，以统一的js方法暴露给web，并形成API文档。这样web能够通过这些API文档，实现更多的功能，达到App不更新的情况下，实现更多需求。
> 例如：是否登录is_login；账号类型account_type；跳转登录do_login；跳转到某个分类的视频列表：show_video_categary，等等

1. 引入JSBridge实现Hybrid API（iOS:[WebViewJavascriptBridge](https://github.com/marcuswestin/WebViewJavascriptBridge) / Android:[jsBridge](https://github.com/lzyzsd/JsBridge)）简化原生和web之间的交互调用 

1. 在Url里面定义好需要原生展示的内容、或执行的方法，例如： 
> Url: **loadData.php?id=abcd&title=Title&title_buttons=Add**
> 
> 那么当App加载这个地址时服务器会返回**id=abcd**的数据，同时App检测到title和buttons参数，会显示**Title标题**，然后在标题栏上加上**新增按钮**。这些都不用等到网页加载出来。
![加载中](/blog/post_images/hybrid-app-brief-talk-04.png)
1. 在加载的过程中把webview隐藏，等到web加载成功后，在通过动画效果之类的把webview展示出来，避免用户看到整个web的渲染过程。特别是html已经渲染出来，但是css或js还没有完成，用户看到的就是一个**不正常的界面**了。
![渲染中](/blog/post_images/hybrid-app-brief-talk-05.jpg)

1. App中web部分的实现，要更多考虑细节的，因为web实现的界面，天生就缺乏一些原生自带的特性。细节处理不到位，会显得App很粗糙。

1. **App必须更多的考虑用户网络不稳定的问题**，并针对性的在模拟不同网络环境去测试、优化Hybrid模块的功能。


# 参考
1. [真正的Hybrid APP没你想的那么简单](http://software.it168.com/a2014/0925/1669/000001669385.shtml)
2. [别闯进Hybrid App的误区](http://www.infoq.com/cn/articles/hybridapp-misunderstanding/)
3. [在微信还没统一所有应用前，Hybrid APP或许会先吃掉你的整个手机](http://36kr.com/p/5036836.html)
4. [聊聊WEB APP、HYBRID APP与NATIVE APP的设计差异](http://mux.baidu.com/?p=6750)
5. [混合模式(Hybrid)App开发概述](http://www.cnblogs.com/yeahui/p/5026587.html)
6. [如何区别一个 App 是 Native App， Web App 还是 Hybrid app？](https://www.zhihu.com/question/23622875)
7. [淘宝app属于hybrid app吗？](https://www.zhihu.com/question/28469978)
8. [how to build fast hybrid ios apps](http://sssslide.com/speakerdeck.com/lokimeyburg/how-to-build-fast-hybrid-ios-apps)
9. [跨终端Web之Hybrid App](http://www.infoq.com/cn/articles/hybrid-app)
10. [如何评价 React Native？](https://www.zhihu.com/question/27852694)
11. [豆瓣混合开发实践](http://lincode.github.io/Hybrid-Rexxar)
12. [Hybrid APP架构设计思路](https://segmentfault.com/a/1190000004263182)

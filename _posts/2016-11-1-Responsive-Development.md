---
layout:    post
title:     "响应式开发"
subtitle: "Responsive Development "
date:       2016-11-1 21:58:35
author:     "Gcelaor"
header-img: "img/Responsive.jpg"
catalog: true
tags:
    - 响应式开发
---
# 响应式开发
### 1.1 响应式概念

响应式网站是一个多项技术构成的设计理念，实现利用一套代码，实现网站对不同分辨率，不同尺寸，不同类型的浏览终端自适应适配，并且在不同类型的终端上显示不同风格的设计。

### 1.2 响应式技术构成

- flexible grid layout 弹性网格布局
- flexible image 弹性图片
- media queries 媒体查询

### 1.3 响应式网站的优点

1. 减少工作量
   - 网站、设计、代码、内容只需要一份
   - 多出来的工作量只是JS脚本、CSS样式做一些改动
2. 节省时间
3. 每个设备都能得到正确的设计
4. 搜索优化
5. 更好的用户体验

### 1.4 响应式网站的缺点

1. 会加载更多的样式和脚本资源，影响加载速度
2. 设计比较难精确定位和控制
3. 老版本的浏览器兼容性不好

### 1.5 Browser

Browser market（china）[statcounter](http://gs.statcounter.com/]) 

1. PC端国内主流浏览器：
   - Chrome浏览器（推荐开发者使用）
   - IE浏览器 8+ / Edge浏览器（市场份额逐渐下降）
   - Firefox浏览器
   - Safari浏览器
2. 移动端国内主流浏览器：
   - Android Browser
   - Chrome浏览器
   - UC浏览器
   - 腾讯X5内核浏览器（如微信、QQ、QQ空间、QQ浏览器）
   - iOS Safari浏览器

### 1.6 媒体查询

```
CSS3：
     @media all and(min-width:800px) and (orientation:landscape){
    ......
    //@media申明类型
    //all代表媒体类型，可为print(打印)或者是screen（屏幕显示）
    //and（逻辑操作符）
}
```

1. 逻辑操作符
   - and：与，操作符左右都满足为真
   - or：或，操作符左右有一个满足为真，可用逗号替代
   - not：非，后跟的表达式，只对逗号或or以前的表达式有效，类似于括号
     `例如：@media (not(screen and(colod))),print and (color){}`
   - only：只有，防止老旧浏览器不兼容
     `例如：@media = "only screen and（min-width:401px）and (max-width:600px)`
     `等效于 @media = "only" //only后跟的所有样式都会失效，都不会显示`
     `@media = "screen and（min-width:401px）and (max-width:600px)`
     `等效于 @media = "screen" //screen后跟的所有逻辑操作符失效，都会显示该媒体查询内的样式`
2. CSS3媒体属性简介

- width：视口宽度
- height：视口高度
- device-width：渲染表面的宽度，就是设备屏幕的宽度
- device-width：渲染表面的高度，就是设备屏幕的高度
- orientation：检查设备处于横向还是纵向
- aspect-ratio：基于视口宽度和高度的宽高比，width/height，如16:9,4:3
- //device-aspect-ratio：渲染表面的宽度，屏幕的宽度
- color：每种颜色的位数bits，如min-color:16位,8位
- resolution：检测屏幕或打印机的分辨率，如min-resolution：300dpi

\-

### 1.7 viewport视口

1.布局视口（layout viewport）

![img](https://i.imgur.com/hOV60TG.png)

布局视口为网页PC端版式，为默认布局模式下的页面显示大小

2.可视视口（visual viewport）

![img](https://i.imgur.com/ac5ygtU.png)

可视视口为手机端能看见PC端网页的显示大小，根据屏幕大小不同，显示大小也会不同

3.理想视口（ideal viewport）

> 理想视口就是布局视口在一个设备上的最佳显示大小，根据屏幕大小自动修改布局视口的尺寸

4.视口设置代码

> ```
> 其中：百度的viewport
> <meta name = "viewport" content="
> width=device-width， //指将视口宽度定义为设备宽度
> minimum-scale=1.0，  //最小的缩放比例为1倍
> maximum-scale=1.0，  //最大的缩放比例为1倍
> user-scalable=no/>   //禁止用户缩放
> ```

### 1.8 响应式网站设计实践原则

1. 开发模式
   - progressive enhancement 渐进增强：先从较低版本，兼容性较差的浏览器开始开发，实现“能用”，再逐渐往上开发，增加效果，实现“好看”，此观念比较老旧
   - graceful degradation 优雅降级：直接从最新版本的浏览器入手开发，之后做老旧浏览器的兼容性适配
2. PC端和手机端的优先原则
   - 要根据网站的需求和性质来选择，主要面向手机端用户的网站要选择手机端优先
   - 根据团队或个人的习惯来选择，没有对错，只有适合
3. 浏览器适配原则（优先chrome上调试）
   - PC端：Chrome、Firefox、IE8+、Safari
   - 手机端：Google Browas、Safari、QQ浏览器、UC浏览器、360浏览器
4. 内容显示原则
   - 不管设备大小，内容可根据页面排版做部分修改，选择显示或隐藏
5. 断点选择原则（具体断点选择和设计师交流）
   - 0-480 小屏幕
   - 481-800 中屏幕
   - 801-1400 大屏幕
   - 1400+ 巨屏幕

## 2 组织项目文件目录结构

### 2.1 基本目录结构

1. src //文件资源文件夹
   - css //样式表文件夹
   - js  //Javascript文件夹
   - img //图片文件夹
   - tpl //模板文件夹
   - swf //Flash文件
   - less //动态样式表，或者sass
2. doc //文档文件夹

### 2.2 常规文件

1. CSS
   - main.css //通用样式文件 
   - normalize.css //
   - page.css //独立页面对应的CSS文件
2. JS
   - main.js //通用JS文件
   - vendor //网站引用的库文件夹
   - vendor/jquery.min.js //jquery压缩版js文件

### 2.3 非常规文件

1. robots.txt

   - 路径：/src
   - 作用：用来告诉搜索引擎爬虫，该网站可访问和不可访问的页面路径，会被爬虫第一时间访问，并依据该文件爬取网站页面

2. favicon.ico

   - 路径：/src
   - 作用：用来被引用为网站的图标，可利用[比特虫](http://www.bitbug.net)等在线工具转换。

3. humans.txt

   - 路径：/src
   - 作用：用来说明参加网站创建人员的信息，如团队成员、感谢和站点的技术信息。[点我进入官网](http://www.humanstxt.org.cn)

4. .editorconfig

   - 路径：根目录

   - 作用：用来使不同的代码编辑根据根据该文件显示相同的代码风格，便于程序员在不同IDE中维护，包括缩进格式、编码格式、换行规格。[点我进入官网](http://editorconfig.org)，了解格式

   - 格式：

     > ```
     > #editorconfig.org   注释说明此文档为editorconfig文件
     >
     > root = true   最顶层的配置文件，之后再不会查找其他文件
     >
     > [*] 通配符：以下规则应用于所有文件
     > charset = utf-8   所有文件的编码格式为utf-8
     > indent_size = 4   代码缩进的空格数，可为tab
     > indent_style = space代码缩进的样式，为空格
     > insert_final_newline = true   每个文件以空白行结尾
     > trim_trailing_whitespace = true   去除换行行首的空白字符
     >
     > [*.md] 以下规则引用与markdown文件
     > trim_trailing_whitespace =  false //在md文件中，不去除换行行首的空白字符
     > ```

5..gitignore

- 路径：根目录
- 作用：告诉Git版本工具，哪些文件不需要添加到版本管理中，包括操作系统生成文件、IDE产生的临时文件、日志文件、工具自动化生成的文件等

6.LICENSE.txt

- 路径：根目录
- 作用：用来存放许可协议，名称为大写，包括版权声明，开源协议

7.README.md

- 路径：根目录
- 作用：用来存放项目简介、使用方式、相关连接

8.CHANGLOG.md

- 路径：根目录
- 作用：用来存放项目每个版本的更新，以及说明版本号、更新内容、修复了哪些问题等



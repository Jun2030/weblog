#### 01、什么是微信开发

微信对外提供了很多功能（如：聊天，支付，分享，收藏等），同时微信还对外开放了很多的接口与能力。程序员基于这些功能和接口进行的开发，叫做微信开发。



#### 02、开放平台和公众平台

**开发平台：**

+ 是微信对外开发`API`接口的平台
+ 开发的 `API`接口，供第三方网站和 `App` 调用
+ 后端程序员是开放平台的主力军

**公众平台：**

+ 是基于微信公众号，为微信用户提供服务的平台
+ 所用公众号，都属于微信内开发
+ 前端程序员是公众开发的主力军



#### 03、小程序出现的目的

拦截用户流量入口，用户的大多数应用需求，都能够在 微信小程序中得到满足



#### 04、小程序的应用场景

适合做“用完就走”的应用（如：点外卖，打车，代驾，共享单车，购物等）

不适合做“重度依赖”的应用（如：大型手机游戏，音乐播放器，视频软件，直播软件等）



#### 05、小程序与传统App的区别

**App：**基于手机操作系统提供的API进行开发，直接安装并运行在手机操作系统之上

**小程序：**基于微信提供的API进行开发，必须基于手机微信才能安装和运行



#### 06、小程序项目结构

+ `minigrogram` 【目录】项目目录
  + `components` 【目录】存放组件的目录
  + `images` 【目录】存放图片的目录
  + `pages` 【目录】存放所有的小程序页面目录
    + `index` 【目录】index页面
      + `index.wxml` 【文件】 index页面的结构
      + `index.js` 【文件】index页面的逻辑
      + `index.json` 【文件】index页面的配置
      + `index.wxss` 【文件】index页面的样式
    + `logs` 【目录】logs页面
      + `logs.wxml` 【文件】logs页面的结构
      + `logs.js` 【文件】logs页面的逻辑
  + `style` 【目录】存放样式的目录
  + `app.js` 【文件】小程序逻辑
  + `app.json` 【文件】小程序的公共配置
  + `app.wxss` 【文件】小程序的公共样式
  + `sitemap.json` 【文件】配置小程序是否被微信索引
+ `project.config.json` 【文件】 开发工具配置文件



#### 07、小程序常用的UI组件

**1. icon图标**

+ `type`：icon的类型，有效值有 `success/success_no_circle/info/warn/waiting/cancel/download/search/clear` ,String类型。
+ `size`: icon的大小，默认值为23，Number/String类型。
+ `color`: icon的颜色，String类型。

**2. view视图容器（相当于网页开发中div标签）**

+ `hover-class`: 指定按下去的样式类。当 `hover-class="none"` 时，没有点击态效果。默认为none，类型是String。
+ `hover-stop-propagation`: 指定是否阻止本节点的祖先节点出现点击态。默认false，boolean类型。
+ `hover-start-time`: 按住后多久出现点击态，单位毫秒。默认值是50，类型是number。
+ `hover-stay-time`: 手指松开后点击态保留时间，单位毫秒。默认值400，类型是number。

**3. text文本**

+ `selecttable`: 文本是否可选择，除了text组件之外，其他组件都无法长按选中，默认false，boolean类型。
+ `space`: 显示连续空格，可选择：`ensp`(英文空格)，`emsp`(中文空格)，`nbsp`，默认值false，String类型。
+ `decode`: 是否解码，可解析：`&nbsp; &lt; &gt; &amp; &apos; &ensp; &emsp;`

**4. button按钮**

+ `size`: 按钮的大小。合法值为：`default/mini`。默认值default，类型String。
+ `type`: 按钮的样式类型。合法值为：`primary(绿色)/default(白色)/warn(红色)`默认值default，类型String。
+ `plain`: 按钮是否镂空，背景色透明。默认值default，类型boolean。
+ `disabled`: 是否禁用。默认值false，类型boolean。
+ `loading`: 名称前是否带loading图标。默认值false，类型boolean。

**5. input输入框**

+ `value`: 输入款的初始内容。类型String。
+ `type`: input的类型。合法值为：`text/number/idcard/digit`。默认值：‘text’，类型String。
+ `password`: 是或否是密码类型。默认值false，Boolean类型。
+ `placeholder`: 输入框为空时占位符。类型String。
+ `disabled`: 是否禁用。默认值false，类型为boolean。
+ `maxlength`: 最大输入长度，设置为-1时不限制最大长度。默认值140，类型Number。

**6. image图片**

+ `src`: 支持本地和网络上的图片
+ `mode`: 指定图片裁剪,合法值为：`scaleToFill/aspectFit/aspectFill/widthFix/heightFix`等。默认值：’scaleToFill‘缩放的模式
+ 组件默认宽度为300px,高度为225px，即使写一个空标签：`<image></image>`



#### 08、WXSS和CSS的区别

不同点是：wxss扩展的特性有：尺寸单位，样式导入。



#### 09、小程序的API

**API概念：**

API应用程序编程接口，是一些预先定义的函数，目的是提供应用程序与开发人员基于某软件或硬件得以访问一组例程的能力。

**API的三种分类：**

1. 事件监听API

   以 `on` 开头的API用来监听某个事件是否触发。

2. 同步API

   以 `sync` 结尾的API都是同步API。

3. 异步API（类似网页端的ajax）

   通常需要指定回调函数接受调用的结果。小程序中，大多数的API都是异步API。



#### 10、组件和API的区别

**相同点：**都是微信官方提供，目的都是为了方便小程序的快速开发

**不同点：**组件以UI结构布局为主，一般不需要处理业务逻辑；API以纯业务逻辑为主，一般没有对应的UI



#### 11、小程序成员管理

登录小程序账号 --> 管理 --> 成员管理 --> 项目成员

**开发者权限：**开发模块权限，可使用体验版小程序，开发者工具

**运营者权限：**管理，推广，设置等模块，可使用体验版小程序

**数据分析者：**统计模块权限，可使用体验版小程序



#### 12、小程序的唯一标识

`appid`



#### 13、WXML和CSS

**1. WXML结构标签**

结构：`text` ，`view` , `button` , `input` , `image` 等。

**2. CSS**

 1.  选择器

     标签选择器，class选择器，id选择器，伪类伪元素选择器，**data-自定义属性选择器**，nth-child, nth-of-type 子类选择器

     ```html
     <!-- wxml -->
     <view data-color="red">字体颜色为红色</view>
     ```

     ```css
     /** wxss **/
     [data-color="red"] {
         color: red;
     }
     ```

 2.  组合选择器的优先级

     !important > style > id > class > 标签 > *

 3.  CSS模块化（模块内部不影响外部：模块独立性，使用导入功能进行相互调用）

     + vue: scoped
     + 小程序: 样式导入

 4.  适配问题

     网页用rem，小程序用rpx。

     rpx 是微信小程序独有的，解决屏幕自适应的尺寸单位。统一规定： 在横向上屏幕分为750份rpx。

     rpx对最终显示的css单位的对应关系： 1rpx = 0.5px。

     官方建议，开发小程序时，设计师可以用iphone6作为视觉稿的标准。

 5.  @import样式导入

     可以导入外联样式表，语法格式为：@import “wxss样式表的相对路径”；（！！分号一定要带上）

 6.  全局样式和局部样式

     全局样式：定义在app.wxss中的样式为全局样式，作用于每一个页面。

     局部样式：定义在page中的样式为局部样式，只作用于对应的页面。

     当局部样式的权重大于或等于全局样式的权重时，才会覆盖全局的样式效果。

     

#### 14、app.json配置文件作用

用来对微信小程序进行全局配置，它决定了页面文件的路径、窗口表现、设置网络超时时间、设置多tab等。

在`app.json`配置文件中，最主要的额配置节点（属性）是：**pages数组**、**window对象**、**tabBar对象**。

+ pages数组

  用来指定小程序由哪些页面组成，每一项都对应一个页面的 **路径 + 文件名** 信息。**文件名不需要写文件后缀**，框架会自动取寻找对应位置的`.json`,`.js`,`.wxml`,`.wxss`四个文件进行处理。

  !> 1. 数组的第一项代码小程序的初始页面（首页）2. 小程序中新增/减少页面，都需要对pages数据进行修改

+ window对象

  用于设置小程序的状态栏，导航条，标题，窗口背景色。

  window节点常用配置项：

  + `backgroundColor`: 窗口的背景色，也是下拉刷新区域的背景色
  + `backgroundTextStyle`: 下拉刷新loading样式（3个小圆点的颜色），仅支持 `dark/light`
  + `navigationBarBackgroundColor`: 导航栏背景颜色
  + `navigationBarTitleText`: 导航栏标题文字内容
  + `enablePullDownRefresh`: 是否开启下拉刷新
  + `navigationBarTextStyle`: 导航栏标题颜色，仅支持`dark/light`

+ tabBar对象

  是移动端应用常见的页面效果，用于实现多页面的快速切换。小程序中通常将其分为 底部tabBar 和 顶部tabBar。

  !> tabBar中，只能配置最少2个，最多5个tab标签，当渲染顶部tabBar的时候，不显示icon，只显示文本
  
  tabBar节点常用配置项：

  + `color`: tab上文字默认颜色

  + `selectedColor`: tab上文字选中时的颜色

  + `list`: tab的列表，最少2个，最多5个

    + `pagePath`: 页面路径，必须在 `pages` 中先定义
  + `text`: tab上按钮文字
    + `iconPath`: icon图标路径，建议尺寸 81px * 81px，图片大小限制为40KB
    + `selectedIconPath`: 选中时的icon图片路径，建议尺寸 81px * 81px
  
    

#### 15、页面/全局配置的关系

app.json中的window节点，可以全局配置小程序中每个页面的窗口表现，如果某些小程序页面想要拥有特殊的窗口表现，此时，页面级别的.json配置文件即可实现这种需求。

**总结：页面级别的配置优先于全局配置生效。**



#### 16、小程序的生命周期

**生命周期（Life Cycle）**：是指一个对象从 创建 --> 运行 --> 销毁 的整个阶段，强调的是一个时间段。

在小程序中，包含两种类型的生命周期：

1. 应用生命周期：特指小程序从 启动 --> 运行 --> 销毁 的过程
2. 页面生命周期：特指小程序中，每个页面的 加载 --> 渲染 --> 销毁 的过程

其中，页面的生命周期范围较小，应用程序的生命周期范围较大。

**生命周期函数**：由3小程序框架提供的内置函数，会伴随着生命周期，自动按次序执行。它的作用是允许在特定的生命周期的时间点上，执行某些特定的操作。

!> 生命周期强调的是时间段，而生命周期函数强调的是时间点。

**生命周期函数分类**

1. 应用生命周期函数

   `app.js` 是小程序执行的入口文件，在 `app.js` 中必须调用 `app()` 函数，`app()` 函数是用来注册并执行小程序的。`app(Object)` 函数接受一个Object参数，通过这个Object参数，指定小程序的生命周期函数。

   Object参数：

   + `onLaunch()`: 生命周期回调-监听小程序初始化，全局只触发一次
   + `onShow()`: 生命周期回调-监听小程序启动或切前台
   + `onHide()`: 生命周期回调-监听小程序切后台

2. 页面生命周期函数

   每个小程序页面，必须拥有自己的`.js`文件，且必须调用 `Page()` 函数，否则会报错。其中 `Page()` 函数用来注册小程序页面。`Page(Object)` 函数接受一个Object参数，通过这个Object参数，指定页面的生命周期函数。

   Object参数：

   + `onLoad()`: 生命周期回调-监听页面加载，页面加载时触发，一个页面只会调用一次，可以在`onLoad`的参数中获取打开当前页面路径中的参数
     + `query`: 打开当前页面路径中的参数
   + `onShow()`: 生命周期回调-监听页面显示，页面显示/切入前台时触发
   + `onReady()`: 生命周期回调-监听页面初次渲染完成，一个页面只会调用一次，代表页面已经准备妥当，可以和视图进行交互。
     + `wx.setNavigationBarTitle`需要在`onReady()`之后进行
   + `onHide()`: 生命周期回调-监听页面隐藏，页面隐藏/切入后台时触发，如调用：`wx.navigateTo()`、`wx.switchTab()`
   + `onUnload()`: 生命周期回调-监听页面卸载，如调用：`wx.redirectTo()`、`wx.navigateBack()`



#### 17、数据绑定

1. 定义页面的数据

   `.js` 文件内可以定义页面的**数据，生命周期函数，其他业务逻辑**。如果要在 `.js` 文件内定义数据，只需**把数据定义到data节点下**即可。

2. Mustache词法格式

   把data中的数据绑定到页面中渲染，使用Mustache语法（双花括号）将变量包起来即可。

   Mustache语法的主要应用场景（绑定内容，绑定数据，运算）：

   + 绑定内容

     ```html
     <!-- 页面结构 -->
     <view>{{message}}</view>
     ```

     ```javascript
     // 页面数据
     Page({
         data: {
             message: "hello World"
         }
     })
     ```

   + 绑定属性

     ```html
     <!-- 页面结构 -->
     <view id="item-{{id}}"></view>
     ```

     ```javascript
     // 页面数据
     Page({
         data: {
             id: 0
         }
     })
     ```

   + 运算（三元表达式，算术运算，逻辑判断，字符串运算，数据路径运算）

     ```html
     <!-- 页面结构 -->
     <view>{{flag ? '条件为真' : '条件为假'}}</view>
     ```

     ```javascript
     // 页面数据
     Page({
         data: {
             flag: true
         }
     })
     ```



#### 18、事件

事件是视图层到逻辑层的通讯方法。

事件可以将用户的行为反馈到逻辑层进行处理。

事件可以绑定在组件上，当组件触发事件，就会执行逻辑层中对应的事件处理函数。

事件可以携带格外信息，例如：id, dataset, touches（有几个手指触碰了组件）

**bindtap绑定触摸事件:**

在小程序中，不存在click点击事件，是通过tap事件来响应触摸行为的。

1. 通过`bindtap`，可以为组件绑定触摸事件
2. 在相应的Page定义中写上相应的事件处理函数，事件参数是`event`:

```html
<!-- 页面结构 -->
<view bindtap="tapName">点击我</view>
```

```javascript
// 页面数据
Page({
    tapName(event) {
        console.log(event);
    }
})
```

**bindinput文本框输入事件：**

1. 通过`bindinput`， 可以为文本框绑定输入事件
2. 在相应的Page定义中写上相应的事件处理函数，事件参数是`event`:

```html
<!-- 页面结构 -->
<input bindinput="inputName"></input>
```

```javascript
// 页面数据
Page({
    inputName(event) {
 		console.log(event);       
    }
})
```

**data和文本框之间的数据同步：**

1. 第一步：手动监听文本框输入事件，通过时间参数event,能够访问到文本框的最新值

2. 第二步：修改data中的数据，通过`this.setData()` 方法，可以给页面中的data数据重新赋值

   ```html
   <!-- 页面结构 -->
   <view>
       <text>输入的内容为：{{inputText}}</text>
       <input bindtap="inputName" value="{{inputText}}"></input>
   </view>
   ```

   ```javascript
   // 页面数据
   Page({
   	data: {
           inputText: ""
       },
       inputName(event) {
       	let inputValue = event.detail.value;
       	this.setData({
               inputText: inputValue
           })
     	}
   })
   ```

**事件传参：**

1. 第一步：通过data-*自定义属性传参

2. 第二步：获取data-*自定义属性中传递的参数

   ```html
   <!-- 页面结构 -->
   <button bindtap="btnHandler" data-parameter="{{123}}"></button>
   ```

   ```javascript
   // 页面数据
   Page({
       btnHandler(event) {
           let query = event.currentTarget.dataset;
           console.log(query.parameter); // > 123
       }
   })
   ```

!> 不能在绑定事件的同事传递参数，以下方式会报错

 ```html
<!-- 页面结构 -->
<button type="primary" bindtap="btnHandler(123)"></button>
 ```



#### 19、条件渲染

**1. wx:if**

使用 `wx:if="{condition}"` 来判断是否需要渲染该代码块

```html
<!-- 页面结构 -->
<view wx:if="{{length > 5}}">5</view>
<view wx:elif="length > 3}}">3</view>
<view wx:else>0</view>
```

**2. block wx:if**

因为 `wx:if` 是一个控制属性，需要将它添加到一个标签上，如果要一次性判断多个组件标签，可以使用 `<block></block>` 标签将多个组件包装起来，并在上边使用 `wx:if` 控制属性。

`<block></block>`并不是一个组件，它只是一个包装元素，不会在页面中做任何渲染，只接受控制属性。

!> 在使用控制属性（`wx:if/wx:elif/ex:else, wx:for, hidden`）的时候，建议都要使用`<block></block>`。

**3. hidden**

直接使用 `hidden="{{condition}}"` 也能控制元素的额显示和隐藏。

```html
<!-- 页面结构 -->
<block hidden="{{condition}}">
    <view>123</view>
</block>
```

**4. wx:if 和 hidden对比**

类似于VUE中的 `v-if` 和 `v-show` ，`wx:if` 有更高的切换消耗，而 `hidden` 有更高的初始渲染消耗。因此，如果需要频繁切换的情境下，用 `hidden` 更好，如果在运行时条件不大可能改变，则 `wx:if` 较好。



#### 20、列表渲染

**1. wx:for**

在组件上使用 `wx:for` 控制属性绑定一个数组，即可使用数组中各项的数据重复渲染该列表。默认数组的额当前项的下标变量名默认为 `index` ， 数组当前项的变量名默认为 `item` 。

> !!注意：
>
> `wx:key` 为必须，`wx:key`的值以两种形式提供：
>
> 1. 字符串，代表在 for 循环的 array 中 item 的某个属性值（**只需要写属性值**），该属性值需要是列表中唯一的字符串或数字，且不能动态改变。
> 2. 保留关键字 `*this` 代表在 for 循环中 item 本身，这种表示需要 item 本身是一个唯一的字符串或数字。

```javascript
// 页面数据
Page({
    data: {
        list: ["1", "2", "3", "4"]
    }
})
```

```html
<!-- 页面结构 -->
<block wx:for="{{list}}" wx:key="*this">
    <view>索引号为：{{index}}, item的值为：{{item}}</view>
</block>
```

**2. 手动指定索引和当前项的变量名**

使用 `wx:for-item` 可以指定数组当前元素的变量名。

使用 `wx:for-index` 可以指定数组当前下标的变量名。



#### 21、页面渲染

**1. key在列表循环中的作用**

如果列表中项目的位置会动态改变或有新的项目添加到列表中，并且希望列表中的额项目保持自己的特征和状态，需要使用 `wx:key` 来指定列表中项目的唯一的标识符。

**2. key值得注意点**

1. key值必须具有唯一性，且不能动态改变
2. key的值必须是数字或者字符串
3. 保留关键字 `*this` 代表在 for 循环中 item 本身，这种表示需要 item 本身是一个唯一的字符串或数字



#### 22、页面事件

**1. 下拉刷新**

+ 目前下拉刷新有两种：

  + 需要在 `app.json` 的 `window` 选项中 或者 页面配置 中开启 `enablePullDownRefresh`。一般情况下，推荐在页面配置中为需要的页面单独开启下拉刷新行为。
  + 通过 `wx.startPullDownRefresh()` 触发下拉刷新，调用后触发下拉刷新动画，效果与用户手动下拉刷新一致。处理完下拉刷新时，下拉刷新的loading效果会一直显示，不会主动消失，需要调用 `wx.stopPullDownRefresh()` 可以停止当前页面的下拉刷新。

+ 监听下拉刷新事件

  ```javascript
  // 页面数据
  Page({
      onPullDownRefresh() {
          console.log('触发了下拉刷新的事件')
      }
  })
  ```

**2. 上拉加载**

+ 上拉加载的更多的应用场景就是数据的分页加载。在 `app.json` 的 `window` 选项中 或者 页面配置 中设置 `onReachBottomDistance` 。单位为px, 默认50px。

+ 监听上拉加载事件

  ```javascript
  // 页面数据
  Page({
     onReachBottom() {
         console.log('触发了上拉加载事件')
     } 
  })
  ```

**3. 用户滑动**

+ 页面在垂直方向已滚动的距离（单位px）

+ 监听滑动页面事件：

  ```javascript
  // 页面数据
  Page({
      onPageScroll(event) {
          console.log('页面的滑动距离为：' event.scrollTop)
      }
  })
  ```

**4. 转发事件**

+ 只有定义了此事件处理函数，右上角菜单才会显示“转发”按钮

+ 此事件处理函数需要 return 一个 Object，用于自定义转发内容

+ object参数

  + `from`: 转发事件来源：`button`:页面内转发按钮/ `menu`:右上角转发菜单
  + `target`: 如果 `from`值是 `button`，则 `target` 是触发这次转发事件的 `button`, 否则为 `undefined`
  + `webViewUrl`: 页面中包含web-view组件时，返回当前web-view的url

  + return自定义转发内容
    + `title`: 转发标题
    + `path`: 转发路径
    + `imageUrl`: 自定义图片路径，显示图片长宽比为5:4

  ```javascript
  Page({
     	onShareAppMessage: function (res) {
    		if(res.from === 'button') {
      	// 来自页面内转发按钮
      	console.log(res.target);
    		}
    		return {
      		title: '音乐',
      		path: 'pages/playlist/playlist',
      		imageUrl: '../../images/share_img.jpg'
    		}	
  	}
  })
  
  ```

**5. tab事件**

+ 当前是tab页时，点击tab时触发

+ Object参数
  + `index`: 被点击tabItem的序号，从0开始
  + `pagePath`: 被点击tabItem的页面路径
  + `text`: 被点击tabItem的按钮文字



#### 23、页面导航

页面导航就是页面之间的跳转，小程序页面之间的导航有两种方式：

1. 声明式导航。
2. 编程式导航。

**1. 声明式导航：**通过点击 navigator 组件实现页面跳转的方式

+ 导航到非tabBar页面。后面可以携带参数。

  ```html
  <navigator url="/pages/logs/logs?name=devin&age=20">导航到logs页面</navigator>
  ```

+ 导航到tabBar页面指。如果 `navigator` 单纯使用 `url` 属性，无法导航到tabBar页面，需要结合 `open-type` 进行导航

  ```html
  <navigator url="/pages/home/home" open-type=switchTab>导航到home页面</navigator>
  ```

+ 后退导航。如果要后退到上级页面或多级页面，需要把 `open-type` 设置为 `navigateBack` , 同时使用 `dalta` 属性指定后退的层数

  ```html
  <navigator open-type="navigateBack" dalta="1"></navigator>
  ```

**2. 编程式导航：**通过调用小程序的额API接口实现跳转的方法

+ 导航到非tabBar页面。

  + 通过`wx.navigateTo(object)`方法，实现跳转，但是不能跳转到tabBar页面。

  + object参数：

    + `url`: 跳转路径，可以携带参数。

      ```html
      <!-- 页面结构 -->
      <button bindtap="goToLogs">跳转到logs页面</button>
      ```

      ```javascript
      // 页面数据
      goToLogs() {
          wx.navigateTo({
              url: "/pages/logs/logs?name=devin&age=20"
          })
      }
      ```

+ 导航到tabBar页面。

  + 通过 `wx.switchTab(ojbect)` 方法，实现跳转到tabBar页面，并关闭其他所有非tabBar页面。

  + object参数：

    + `url`: 跳转tabBar页面路径，不能携带参数。

      ```html
      <!-- 页面结构 -->
      <button bindtap="goToHome">跳转到home页面</button>
      ```

      ```javascript
      // 页面数据
      goToHome() {
          wx.switchBar({
              url: "/pages/home/home"
          })
      }
      ```

+ 后退导航。

  + 通过 `wx.navigateBack(object)` 方法，关闭当前页面，放回上一页面或多级页面。
  + object参数：
    + `dalta`: 返回的页面数，如果dalta大于现有页面数，则返回到首页。

**3. 页面接受导航传递的参数**

不论是声明式导航还是编程式导航，最终导航到的页面可以在 `onLoad` 生命周期函数中接收传递过来的参数。

```javascript
// 页面数据
Page({
  onLoad: function (options) {
	console.log(options) // options就是导航传递的参数
  },
})
```

**4. 自定义编译模式快速传参**

小程序每次修改编译后，默认从首页进入，但是在开发阶段，经常会针对特定的页面进行开发，为了方便编译后直接进入对应的页面，可以配置自定义编译模式。步骤：

1. 单击工具栏上的 “普通编辑” 下拉菜单
2. 单击下拉菜单中的 “添加编译模式” 选项
3. 在弹出的 “自定义编译条件窗口” ，按需添加 模式名称，启动页面，启动参数，进入场景等。



#### 24、网络数据请求

**1. 配置服务器域名**

每个小程序需要事先设置一个通讯域名，小程序只可以跟指定的域名进行网络通信。服务器域名在【小程序后台-开发-开发设置-服务器域名】中进行配置，配置时需要注意：

+ 域名只支持https和wss协议
+ 域名不能使用IP地址或者localhost
+ 域名必须经过ICP备案
+ 服务器域名一个月内可申请5次修改

**2. 跳过域名校验**

在微信开发者工具中，可以临时开启：【开发环境不校验请求域名，YSL版本及HTTPS证书】选项，跳过服务器域名校验。此时，开始调试模式时，不会进行服务器域名校验。

!> 在服务器域名配置成功后，建议关闭此选项进行开发，并在各平台开发，以确认服务器域名配置正确。

**3. 发起get请求**

调用 `wx.request(object)` 方法发起get请求。

object参数：

+ `url`: 开发者服务器接口地址
+ `data`: 请求的参数
+ `success`: 接口调用成功的回调函数： `result.data` 就是服务器返回的真实数据。
+ `fail`: 接口调用失败的回调函数。

**4. 发起post请求**

调用 `wx.request(object)` 方法发起get请求。（多了一个method属性）

object参数：

+ `method`: “POST”
+ `header`: 设置请求的header，header中不能设置 Referer。`content-type` 默认为 `application/json`

**5. 小程序中没有跨域限制**

普通网站开发中，由于浏览器的同源策略限制，存在数据的跨域请求问题，衍生出了 `JSONP` 和 `CORS` 两种主流跨域解决方案。小程序的代码并不运行在浏览器中，所以小程序开发中，不存在数据跨域请求问题。



#### 25、组件的创建与引用

**1. 创建组件**

1. 在项目的根目录中，鼠标右键，创建 components –> test文件夹
2. 在新建的 components –> test 文件夹上，鼠标右键，点击 新建Component
3. 为新建的组件命名之后，会自动生成组件对应的4个文件，后缀名分别为 `.js` `.json` `.wxml` `.wxss`

**2.引用组件**

1. 在需要引用组件的页面中，找到页面的 `.json` 配置文件，新增 `usingComponents` 节点
2. 在 `usingComponents` 中，通过键值对的形式，注册组件；键为注册的组件名称，值为组件的相对引用路径
3. 在页面的 `.wxml` 文件中，把注册的组件名称，以标签形式在页面上使用，即可把组件展示到页面上

**3. 使用样式美化组件**

组件对应的 `wxss` 文件的样式，只对组件的 `wxml` 内的节点生效。编写组件样式时，需要注意：

+ 组件和引用组件的页面不能使用id选择器（`#a`）,属性选择器（`[a]`）和标签名选择器，请改用class选择器
+ 组件和引用组件的页面中建议不使用后代选择器（`.a .b`）
+ 子元素选择器（`.a > .b`）只能用于 view 组件与其子节点之间
+ 继承样式，如：`font`, `color`，会从组件外继承到组件内
+ 除继承样式外， `app.wxss` 中的样式、组件所在页面的样式对自定义组件无效

#### 26、组件的data与methods

**1. 使用data定义组件的私有属性**

页面的data定义在 `Page()` 函数中，组件的data定义在 `component()` 函数中。

+ 在组件的 `.js` 中，如果要访问data中的属性，直接使用 `this.data.数据名称` 即可。若要为data中的数据重新赋值，调用 `this.setData({数据名称： 新值})` 即可。
+ 在组件的 `.wxml` 中，如果要渲染data中的数据，直接使用 `{{数据名称}}` 即可。

**2. 使用methods定义组件的事件处理函数**

组件的事件处理函数，必须定义在 `methods` 节点中。



#### 27、组件的properties

**1. properties的作用**

+ 类似于vue组件中的 `props` ,小程序组件中的 `propereties` ，是组件的对外属性，用来接收外界传递到组件中的数据。

+ 在小程序中，`properties` 和 `data` 的用法类似，他们都是可读可写的。不过， `data` 更倾向于存储组件的私有数据， `properties` 更倾向于存储外界传递到组件中的数据

**2. 声明properties的两种方法**

```javascript
Page({
    propeerties: {
        // 完整的定义方式
        a: {
            type: String,
            value: ""
        },
        // 简化的定义方式
        b: String
    }
})
```

**3. 为组件传递properties的值**

+ 可以使用数据绑定的形式，向子组件的属性传递动态数据。

+ 在定义 `properties` 时，属性名采用驼峰写法（`properCount`）
+ 在 `wxml` 中，指定属性值时，则对应使用连字符写法（`proper-count="attr value"`）
+ 应用数据绑定是，采用驼峰写法（`attr="{{properCount}}"`）

**4. 在组件内修改properties的值**

`properties` 的值是可读可写的，它的用法与 `data` 几乎一致，因此可以通过 `setData` 修改 `properties` 中任何属性的值。

```javascript
properties: {
    count: Number
},
    
methods: {
    add() {
        this.setData({count: this.properties.count + 1})
    }
}
```



#### 28、数据监听器observers

数据监听器可以用来监听和响应任何属性和数据字段的变化，从而执行待定的操作。作用类似于 vue 中的 watch。

1. 监听子数据字段的变化

   + 键： 就是需要被监听的数据
   + 值：就是数据变化之后会触发的事件函数
   + 左侧可以监听单个数据，也可以监听多个数据，监听多个数据时，每个字段之间用英文逗号（`,`）隔开，只要其中有一个字段变化，就会触发值对应的额事件函数

   ```javascript
   Component({
       observers: {
       	'name, propCount': (newName, newPropCount) => {}
   	}
   })
   ```

2. 使用通配符 `**` 监听所有子数据字段的变化

   ```javascript
   Component({
       data: {
           obj: {}
       }
       observers: {
           'obj.**': (newObj) => {}　
       }
   })
   ```

   

#### 29、组件的生命周期

**1. 组件的主要生命周期**

组件的生命周期，指的是组件自身的一些函数，这些函数在遇到一些框架事件会被自动触发。其中，最重要的生命周期是 `created`, `attached`, `detached`,包含一个组件实例生命流程的最主要的时间点。

+ `created`: 组件实例被创建好时被触发。此时还不能调用 `setData()`。一般这个生命周期只用来给组件 `this` 添加一些自定义属性字段
+ `attached`: 在组件完全初始化完毕，进入页面节点数后，`attached` 生命周期会触发。绝大多数初始化工作都可以在这个时机进行
+ `detached`: 在组件离开页面节点数后触发。比如，退出一个页面。

**2. 组件可用的全部生命周期函数**

+ `created`: 组件生命周期函数-在组件实例刚刚被创建时执行，注意此时不能调用 `setData()`
+ `attached`: 组件生命周期函数-在组件实例进入页面节点树时执行`
+ `ready`: 组件生命周期函数-在组件布局完成后执行`
+ `moved`: 组件生命周期函数-在组件实例被移动到节点树另一个位置时执行`
+ `detached`: 组件生命周期函数-在组件实例被从页面节点树移除时执行

**3. 定义生命周期函数**

组件的生命周期需要在 `lifetimes` 字段内进行声明。（这是推荐方式）

```javascript
Component({
    lifetimes: {
        attached() {},
        detached() {}
    }
})
```

**4. 组件所在页面的生命周期**

组件所在页面的生命周期在 `pageLifetimes` 定义段中定义，其可用的生命周期包括：

```javascript
Component({
    pageLifetimes: {
        show() {},
        hide() {},
        resieze() {}
    }
})
```



#### 30、组件插槽

**1. 默认插槽**

在组件的 `wxml` 中可以包含 `slot` 节点，用于承载组件使用者提供的 `wxml` 结构。默认情况下，一个组件的 `wxml` 中只能有一个slot。需要使用多 `slot` 时，可以在组件 `js` 中声明启用。

!> 小程序中目前只有默认插槽和多个插槽，暂不支持作用于插槽。

```html
<!-- 组件模板 -->
<view>
	<view>这里是组件的内部节点</view>
    <slot></slot>
</view>
```

```html
<!-- 引用组件的页面模板 -->
<view>
	<component>
        <!-- 组件内的内容会放置到组件<slot>位置上 -->
        <view>这里是插入大组件slot中的内容</view>
    </component>
</view>
```

**2. 启动多个插槽**

在组件中，需要使用多个 `slot` 时，可以在组件 `js` 中声明启用：

```javascript
Component({
    options: {
        multipleSlots: true
    }
})
```

**3. 定义多个插槽**

可以在组件的 `wxml` 中使用多个 `slot` 标签，以不同的 `name` 来区分不同的插槽。

```html
<!-- 组件模板 -->
<view>
    <slot name="before"></slot>
	<view>这里是组件的内部节点</view>
    <slot name="after"></slot>
</view>
```

**4. 使用多个插槽**

使用时，用 `slot` 属性来将节点插入到不同的 `slot` 中。

```html
<!-- 引用组件的页面模板 -->
<view>
	<component>
        <view slot="before">这里是插入组件slot中before的内容/view>
        <view slot="after">这里插入到组件slot中after的内容</view>
    </component>
</view>
```



#### 31、组件中的通信

**1. 组件之间的三种 基本通信方式**

   	1. `wxml` 数据绑定：用于父组件向子组件的指定属性传递数据。
            	2. 事件：用于子组件向父组件传递数据，可以传递任何数据。
         	3. 父组件通过 `this.selectComponent` 方法获取子组件实例对象，可以直接访问组件的任意数据和方法。

**2. this.selectComponent(String)**

在小程序的组件中，调用 `this.selectComponent(String)` ，可以返回指定组件的实例对象。

```html
<component id="cA"></component>
```

```javascript
Page({
    onLoad() {
        let component = this.selectComponent("#cA");
        console.log(component);
    }
})
```

**3. 通过事件监听实现子向父传值**

事件系统是组件间通信的主要方式之一。自定义组件可以触发任意的事件，引用组件的页面可以监听这个事件。

通过事件监听实现子组件向父组件传值的步骤：

1. 在父组件的 `js` 中，定义一个函数（`a()`），这个函数（`a()`）即将通过自定义事件的形式，传递给子组件
2. 在父组件的 `wxml` 中，通过自定义事件的形式，将步骤1中定义的函数引用（`a="b"`），传递给子组件
3. 在子组件的 `js` 中，通过调用 `this.triggerEvent("b", detail)`,将数据发送到父组件
4. 在父组件的 `js` 中，通过 `e.detail` 获取到子组件传递过来的数据



#### 32、框架函数-APP()

`App(Object object)`

+ 注册小程序。接受一个`Object`参数，其指定小程序的生命周期回调等。

+ `App()`必须在 `app.js`中调用，必须调用且只能调用一次。

+ 参数

  + `onLaunch()`: 生命周期回调-监听小程序初始化，全局只触发一次

  + `onShow()`: 生命周期回调-监听小程序启动或切前台

  + `onHide()`: 生命周期回调-监听小程序切后台

  + `onError()`: 错误监听函数，比如发生脚本错误或API调用报错

  + `onPageNotFound()`: 页面不存在监听函数，比如链接到404页面

  + `onUnhandledRejection()`: 未处理的 Promise 拒绝事件监听函数

  + 其他：可以定义任意函数或者变量到`Object`参数中，用`this`可以访问

    ```javascript
    //app.js
    App({
      onLaunch: function () {
        console.log("onLaunch 执行");
        
        if (!wx.cloud) {
          console.error('请使用 2.2.3 或以上的基础库以使用云能力')
        } else {
          wx.cloud.init({
            // env 参数说明：
            //   env 参数决定接下来小程序发起的云开发调用（wx.cloud.xxx）会默认请求到哪个云环境的资源
            //   此处请填入环境 ID, 环境 ID 可打开云控制台查看
            //   如不填则使用默认环境（第一个创建的环境）
            env: 'zijun-hv3gt',
            traceUser: true,
          })
        }
    
        this.globalData = {}
      },
    
      onShow(options) {
        console.log("onShow 执行");
        console.log(options);
      },
    
      onHide(options) {
        console.log("onHide 执行");
        console.log(options)
      },
    
      onError(msg) {
        console.log("onError 执行");
        console.log(msg);
      },
    
      onPageNotFound(res) {
        wx.redirectTo({
          url: 'pages/404/404',
        })
      },
    
      globalData: "I am global data"
    })
    ```



#### 33、框架函数-Page()

`Page(Object object)`

+ 注册小程序中的一个页面。接受一个`Object`类型参数，其指定页面的初始数据、生命周期回调、事件处理函数等

+ 参数

  + `data()`: 页面的初始数据，用于页面第一次渲染

  + `onLoad()`: 生命周期回调-监听页面加载，页面加载时触发，一个页面只会调用一次，可以在`onLoad`的参数中获取打开当前页面路径中的参数

    + `query`: 打开当前页面路径中的参数

  + `onShow()`: 生命周期回调-监听页面显示，页面显示/切入前台时触发

  + `onReady()`: 生命周期回调-监听页面初次渲染完成，一个页面只会调用一次，代表页面已经准备妥当，可以和视图进行交互。

    + `wx.setNavigationBarTitle`需要在`onReady()`之后进行

  + `onHide()`: 生命周期回调-监听页面隐藏，页面隐藏/切入后台时触发，如调用：`wx.navigateTo()`、`wx.switchTab()`

  + `onUnload()`: 生命周期回调-监听页面卸载，如调用：`wx.redirectTo()`、`wx.navigateBack()`

  + `onPullDownRefresh()`: 监听用户下拉动作事件（下拉刷新）

    + 需要在`app.json`的`window`选项中，或者在页面配置中开启 `enablePullDownRefresh`
    + 可以通过 `wx.startPullDownRefresh`触发下拉刷新，当处理完数据刷新后，`wx.stopPullDownRefresh`可以停止下拉刷新动作

  + `onReachBottom()`: 监听用户上拉触底动作事件（上拉触底）

    + 可以在 `app.json` 的 `window` 选项中，或者在页面配置中设置触发距离 `onReachBottomDistance`
    + 在触发距离内滑动期间，本事件只会被触发一次

  + `onShareAppMessage(object)`: 用户点击右上角转发

    + 只有定义了此事件处理函数，右上角菜单才会显示“转发”按钮
    + 此事件处理函数需要 return 一个 Object，用于自定义转发内容
    + object参数
      + `from`: 转发事件来源：`button`:页面内转发按钮/ `menu`:右上角转发菜单
      + `target`: 如果 `from`值是 `button`，则 `target` 是触发这次转发事件的 `button`, 否则为 `undefined`
      + `webViewUrl`: 页面中包含web-view组件时，返回当前web-view的url
    + return自定义转发内容
      + `title`: 转发标题
      + `path`: 转发路径
      + `imageUrl`: 自定义图片路径，显示图片长宽比为5:4

    ```javascript
      /**
       * 用户点击右上角分享
       */
      onShareAppMessage: function (res) {
        if(res.from === 'button') {
          // 来自页面内转发按钮
          console.log(res.target);
        }
        return {
          title: '音乐',
          path: 'pages/playlist/playlist',
          imageUrl: '../../images/share_img.jpg'
        }
      }
    ```

  + `onPageScroll()`: 页面滚动触发事件的函数

    + `scrollTop`: 页面在垂直方向已滚动的距离（单位px）

  + `onResize()`: 页面尺寸改变时触发

  + `onTabItemTap()`: 当前是tab页时，点击tab时触发

    + Object参数
      + `index`: 被点击tabItem的序号，从0开始
      + `pagePath`: 被点击tabItem的页面路径
      + `text`: 被点击tabItem的按钮文字

  + 其他：可以自定义任意函数或数据到 `Object` 参数中，在页面的函数中用 `this` 可以访问，比如自定义事件方法

+ 需要注意的是：Page和Component不同的是，Page自定义事件函数写在Page的参数中，而Component自定义事件函数需写在Component的methods方法中。

  ```javascript
  // Page页面 js
  Page({
      data: {
        // 页面初始化数据  
      },
      
      // ...
      
      goTo404 () {
          wx.navigateTo({
              url: '/pages/404/404'
          })
      }
  })
  ```

  ```javascript
  // Component js
  Component({
      properties: {
          // 组件对外属性
      },
      
      // ...
      
      methods: {
          goTo404 () {
              wx.redirectTo({
                  url: '/pages/404/404'
              })
          }
      }
  })
  ```

+ `getCurrentPages()`: 获取当前页面栈。数组中的第一个元素为首页，最后一个元素为当前页面。

  + 注意：
    + 不要尝试修改页面栈，会导致路由以及页面状态错误
    + 不要在 `App.onlaunch()` 的时候调用 `getCurrentPages()` ，此时 `Page` 还没有生成



#### 34、框架函数-Component()

`Component(Object object)`

+ 创建自定义组件，接受一个 `Object` 类型的参数

+ 生成的组件实例可以在组件的方法、生命周期函数和属性 `observe` 中通过 `this` 访问。

+ 组件通用属性

  + `is`: 组件的文件路径
  + `id`: 节点id
  + `dataset`: 节点dataset
  + `data`: 组件数据，包括内容数据和属性值
  + `properties`: 组件数据，包括内部数据和属性值

+ 组件常用方法

  + `setData`: 设置data并执行视图层渲染

  + `triggerEvent`: 组件触发事件

    + 父组件向子组件传递数据，可以在WXML上进行数据绑定，设置属性

    + 子组件向父组件传递数据，主要通过事件

      + 组件内WXML文件中定义 **引发事件a**

        `<view bindtap: a></view>`

        如果有参数

        `<view bindtap: a data-id="{{x}}" data-name="{{y}}"></view>`

      + 组件内JS文件中,在设置的 **引发事件a** 中触发 **传递事件b** 传递数据

        ```javascript
        a(e) {
            this.triggerEvent('b', detail, option)
        }
        ```

      + 父级页面（组件）WXML文件中，在使用组件上定义 **接收事件c** 和设置 **传递事件b**

        `<com bind:c="b"></com>`

      + 父级页面JS文件中，设置 **接收事件c**

        ```javascript
        c(e) {
        	console.log(e);    
        }
        ```

    ```html
    <!-- Components/playlist/playlist.wxml -->
    <view class="c-playlist-container" bindtap="handleTransmit" data-id="{{palyData.id}}" data-name="{{palyData.name}}">
      <image src="{{palyData.picUrl}}" class="c-playlist-img"></image>
      <view class="c-playlist-tag"><image src="/images/palylist_tag.png"></image><text>{{count}}</text></view>
      <view class="c-playlist-title">{{palyData.name}}</view>
    </view>
    ```

    ```javascript
    // Components/playlist/playlist.js
    Component({
        // ...
        methods: {
            handleTransmit(e) {
                let query = e.currentTarget.dataset;
                let eventDetail = {
                    id: query.id,
                    name: query.name
                };
                let eventOption = {};
                this.triggerEvent("transmitId", eventDetail, eventOption);
            }
        }
    })
    ```

    ```html
    <!-- pages/playlist/playlist.wxml -->
    <view class="playlist-wrap">
    	<block wx:for="{{playlist}}" wx:key="id">
    		<z-playlist paly-data="{{item}}" class="z-playlist" bind:transmitId = "transmitId"></z-playlist>
    	</block>
    </view>
    ```

    ```javascript
    // pages/playlist/playlist.js
    Page({
        // ...
        transmitId(e) {
            console.log(e.detail); // > {id: 102, name: "Chiptune丨探索像素世界"}
        }
    })
    ```

  需要注意的是：

  + Vue中父组件向子组件传递一个对象，子组件改变这个对象，那么父组件也会相应的改变。即数据绑定到子组件是浅拷贝的。而在微信小程序中，经实现，数据绑定则是深拷贝的，子组件修改传递的对象，不会影响到父组件的这个对象。

    ```html
    <!--- pages/playlist/playlist.wxml -->
    <view>
    	<z-playlist transmit-data="{{transmitData}}"></z-playlist>
    </view>
    ```

    ```javascript
    // pages/playlist/palylist.js
    Page({
        data: {
            transmitData: {
                a: 1,
                b: 2,
                c: 3
            }
        }
    })
    ```

    ```html
    <!-- Components/playlist/playlist.wxml -->
    <view bindtap="handleTransmit">
    </view>
    ```

    ```javascript
    // Components/playlist/playlist.js
    Component({
        properties: {
            transmitData: {
                type: Object
            }
        },
        
        methods: {
            hancleTransmit() {
                console.log(this.data.transmitData);
                this.setData({'transmitData.c': 10});
                console.log(this.data.transmitData);
            }
        }
    })
    ```

    

+ 参数

  + `properties`: 组件的对外属性对象

    + 在 `properties` 定义段中，属性名采用驼峰写法(`propertiesName`)，在 `wxml`中，指定属性值时则对应使用连字符写法(`properties-name="valueName"`)，应用于数据绑定时采用驼峰写法(`valueName`)
    + 定义段
      + `type`: 属性的类型
      + `optionalTypes`: 属性的额类型（可以指定多个）
      + `value`: 属性的初始值

    ```javascript
    // Component js
    Component({
        properties: {
            min: {
                type: Number,
                value: 0
            },
            max: {
                // 这个属性可以是 Number/String/Boolean 三种类型中的一种
                type: Number,
                optionalTypes: [String, Boolean]
                value: 0
            },
            
        }
    })
    ```

  + `data`: 组件的内部数据，和 `properties` 一同用于组件的模板渲染

  + `observers`: 组件数据字段监听器，用于监听 `properties` 和 `data` 的变化

  + `methods`: 组件的方法，包括事件响应函数和任意的自定义方法

  + `behaviors`: 用于组件间代码共享的特性，类似于编程语言中的“mixins”,`每个behaviors`都包含 `properties`(属性)、`data`（数据）、`methods`（方法）、`created/attached/ready/moved/detached`(生命周期函数)，组件引用时，就会合并到当前组件中

    ```javascript
    // 第一步：创建behavior.js 提供组件调用
    // behavior.js
    let myBehavior = Behavior({
        properties: {
            myName: {
                type: String,
                value: "Devin"
            },
            myType: {
                type: String
            }
        },
        
        data: {
            myData: {}
        },
        
        attached: () => {
            console.log("myAttached")
        },
        
        methods: {
            myMethod: () => {
                console.log("myMethod")
            }
        }
    })
    
    export { myBehavior }
    ```

    ```javascript
    // 第二步：在组件中引入
    // components/playlist/playlist.js
    import { myBehavior } from "../../behaviors/hehavior"
    
    Component({
        hehaviors: [mybehavior],
        
        properties: {
            
        },
        
        data: {},
        
        attached: () => {},
        
        methods: {
            
        }
    })
    ```

    ```html
    <!-- components/playlist/playlist.wxml -->
    <view>{{myName}}</view>
    ```

  + `created`: 组件生命周期函数-在组件实例刚刚被创建时执行，注意此时不能调用 `setData()`

  + `attached`: 组件生命周期函数-在组件实例进入页面节点树时执行

  + `ready`: 组件生命周期函数-在组件布局完成后执行

  + `moved`: 组件生命周期函数-在组件实例被移动到节点树另一个位置时执行

  + `detached`: 组件生命周期函数-在组件实例被从页面节点树移除时执行

  + `relations`: 组件间关系定义，比如两个组件是父子节点关系

  + `externalClasses`: 组件接受的外部样式类

  + `options`: 一些选项

  + `lifetimes`： 组件生命周期声明对象，推荐使用

    ```javascript
    // 组件生命周期书写方式
    Component({
        // 这是旧式的定义方式，可以保持对 < 2.2.3 版本基础库的兼容
        attached: () => {},
        detached: () => {},
        
        // 新式的定义方式，推荐使用
        lifetimes: {
            attached: () => {},
            detached: () => {}
        }
    })
    ```

  + `pageLifetimes`: 组件所在页面的生命周期声明对象

    + `show`: 组件所在页面被展示时执行
    + `hide`: 组件所在页面被隐藏时执行
    + `resize`: 组件所在页面尺寸变化时执行

    ```javascript
    // 组件所在页面的生命周期书写方式
    Component({
        pageLifetimes: {
            show: () => {},
            hide: () => {},
            resize: () => {}
        }
    })
    ```

  + `definitionFilter`: 定义段过滤器
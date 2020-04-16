##### 01、官方及文档

* 官方地址：[https://docsify.js.org/#/](https://docsify.js.org/#/)
* 推荐教程：[https://segmentfault.com/a/1190000017576714](https://segmentfault.com/a/1190000017576714)



##### 02、dosify特性

* 无需构建，写完文档直接发布
* 容易使用并且轻量（~19kb gzipped）
* 智能的全文搜索
* 提供多套主题
* 丰富的 API
* 支持 Emoji
* 兼容 IE10+
* 支持 PWA
* 支持 SSR



##### 03、docsify 本地运行

使用 `docsify-cli` 来进行本地开发。具体步骤如下：

1. `npm i docsify-cli -g` , 全局安装 doscify 脚手架工具
2. `mkdir weblog` , 寻找本地磁盘，新建项目目录
3. `cd weblog` , 进入项目目录文件中
4. `docsify init ./docs` , 初始化一个项目，会生成一些文件
5. `docsify serve ./` ， 本地启动服务，即可及时刷新预览



##### 04、常用配置

1. 编辑 `index.html` 中 `window.$docsify` 的 `coverpage` 参数，和创建 `_coverpage.md` 文件即可展示封面。
2. 替换 `index.html` 中 的 `css` 样式，即可改变主题。
3. 编辑 `index.html` 中 `window.$docsify` 的 `loadSidebar` 参数，和创建 `_sizebar.md` 文件即可自定义菜单栏。
4. github设置中，开启 `GitHub Pages` 功能并选择 `master branch / docs folder` 选项。



##### 05、特殊的渲染语法

1. `!> Time is money!`: 重要内容

2. `?> You are my friend`: 普通提示

3. `[link](/demo ':target=_blank')`: 设置超链接的打开方式（`_black/_self`）

4. `[link](/demo ':disaled')`: 超链接禁止点击

5. `![image](url ':size=50%')`: 图片显示大小（`':size=50x100'/':size=100'/':size=20%'`）

6. 隐藏/展开详情

   ``` markdown
   <details>
   <summary>展示文章</summary>
   这是隐藏的内容	
   </details>
   ```

   
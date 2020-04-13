##### 1、docsify 本地运行

使用 `docsify-cli` 来进行本地开发。具体步骤如下：

1. `npm i docsify-cli -g` , 全局安装 doscify 脚手架工具
2. `mkdir weblog` , 寻找本地磁盘，新建项目目录
3. `cd weblog` , 进入项目目录文件中
4. `docsify init ./` , 初始化一个项目，会生成一些文件
5. `docsify serve ./` ， 本地启动服务，即可及时刷新预览



##### 2、特殊的渲染语法

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

   
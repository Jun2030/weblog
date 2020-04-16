##### 01、官方及文档

* 官方地址：[https://hexo.io/](https://hexo.io/)
* 推荐教程：https://hexo.io/zh-cn/docs/index.html](https://hexo.io/zh-cn/docs/index.html)



##### 02、特性

* 超快速度
* 支持Markdown
* 可使用GitHub Pages 托管
* 众多的插件和强大的可扩展性



##### 03、本地运行

1. `npm install hexo-cli -g` 全局安装 `hexo` 脚手架工具，安装完，可以键入 `hexo -v` 查看版本
2. `hexo init myblog` 初始化并创建项目名为 `myblog` 的目录 
3. `cd myblog` 进入创建的项目目录中
4. `npm install` 安装依赖
5. `hexo g`  / `hexo generate` 生成静态文件
6. `hexo s` / `hexo serve` 部署文章



##### 04、安装主题

1. 找到主题源码，比如 `hexo-theme-next`主题，下载链接 [https://github.com/theme-next/hexo-theme-next/releases/](https://github.com/theme-next/hexo-theme-next/releases/)， 下载 `Source code(zip)` 解压到 `themes` 文件夹下，重命名为 `next`
2. 修改配置文件 `_config.yml` ，`theme: next`
3. `hexo g`重新生成静态文件
4. `hexo s` 重新部署






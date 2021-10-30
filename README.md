# 零代码零成本零广告 -- 静态在线个人博客网站搭建与管理的配置代码包(基于Github Pages服务)

> 我们的下一份简历何必是简历!!!

> 一个基于NodeJS环境使用Hexo+Next搭建的个人博客网站代码与配置包.零开发,自动生成博客索引.自动集成全局查询功能;

> 通过GIthub Pages提供的静态页面托管服务,可以实现零成本维护个人在线博客;

## 环境准备

1. Github账号;
2. NodeJS运行环境;

## 工具介绍

* Hexo: [Hexo](https://hexo.io/zh-cn/) 是高效的静态站点生成框架，她基于 [Node.js](https://nodejs.org/)。 通过 Hexo 你可以轻松地使用 Markdown 编写文章，除了 Markdown 本身的语法之外，还可以使用 Hexo 提供的 [标签插件](https://hexo.io/zh-cn/docs/tag-plugins.html) 来快速的插入特定形式的内容。在这篇文章中，假定你已经成功安装了 Hexo，并使用 Hexo 提供的命令创建了一个站点。
* Next: [Next](https://theme-next.iissnan.com/) 是一个基于Hexo的样式插件。

## 安装步骤

* 全局安装hexo模块;

```bash
npm install -g hexo
```

* 克隆下载当前项目至本地;

```bash
git clone https://github.com/guokaia/blog-template.git
```

* 加载node_modules资源包;

```bash
# 移动到 根目录, 加载nexo模块的依赖
cd blog-template
npm install
```

```bash
# 移动到 blog-template/themes/next, 加载next模块的依赖
cd blog-template/themes/next
npm install
```

* 本地启动;

```bash
# 移动到 根目录, 通过启动hexo内置的服务在本地端口访问效果.
hexo s --debug
```

* 浏览器访问(http://localhost:4000);

## 使用方式

* 创建博文;

  * 创建索引

  ```bash
  # 移动到 根目录, 创建文章索引
  cd blog-template
  hexo new "Mekatok开发笔记四:Mekatok开发笔记四-关于系统主动报警与聊天室功能的思考与实现"
  ```

  * 编辑内容,进入目录(blog-template/source/_posts)下,可以看到刚创建的"Mekatok开发笔记四:Mekatok开发笔记四-关于系统主动报警与聊天室功能的思考与实现.md"文件,进入直接编辑即可.浏览器会动态刷新;

* 删除博文;

  * 进入目录(blog-template/source/_posts)下,直接删除Markdown文件即可删除博文;

* 编辑 "关于":

  * 进入目录(blog-template/source/about)下,直接编辑index.md文件即可;

## 配置项

* hexo的配置文件位置在"blog-template/_config.yml",文件内每个配置项都有说明.这个文件主要是设置工具在构建时的一些配置项,比如网站名,副标题,网站备注,博文索引规则和语言等等;
* next的配置文件位置在"blog-template/themes/next/_config.yml",同样每一个配置项都有说明,这个文件主要是设置网站主题样式相关的内容;

## Github Pages

* 创建Github仓库

  PS: 仓库名必须为 {你的github用户名}.github.io --只有这样的仓库名才会被Github默认为Pages服务地址,并可以通过https://{你的github用户名}.github.io直接访问.

* 生成静态资源

```bash
# 移动到 根目录, 生成静态资源
cd blog-template
hexo g
```

* 托管至仓库

  * 直接上传

    将blog-template根目录生成的"public"为根目录上传至第一步创建的仓库即可;

  * 插件上传

    * 修改Github仓库地址
    * 执行上传命令

```bash
// 打开文件 blog-template/_config.yml, 在文件末尾找到
// 将repo的值改为你的上一步仓库的地址
deploy:
  type: git
  repo: https://github.com/guokaia/guokaia.github.io.git
  branch: main
```

``` bash
# 移动到 根目录, 生成静态资源
cd blog-template
hexo d
```

## PS

* 没有科学上网的同学, 上传仓库的时候就多试几次吧...
* 如果有帮到你的地方可不可以给我的另一个仓库 [Mekatok](https://github.com/guokaia/Mekatok) 来个Star...

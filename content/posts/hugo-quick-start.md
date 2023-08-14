---
title: "快速搭建hugo博客"
date: 2023-08-14T14:25:13+08:00
tags: ["github", "hugo"]
---

# 0.前提条件

* [安装git](https://git-scm.com/)

* [安装Hugo](https://github.com/gohugoio/hugo/)（推荐hugo_extended）

# 1.创建网站

在解压后的hugo_extended目录下。

``` cmd
hugo new site quickstart
cd quickstart
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo "theme = 'ananke'" >> hugo.toml
hugo server
```

## 命令解释

在目录中为您的项目创建目录`quickstart`。

``` cmd
hugo new site quickstart
```

跳转到`quickstart`项目根目录。

``` cmd
cd quickstart
```

在当前目录中初始化一个空的 Git 仓库。

``` cmd
git init
```

将[Ananke](https://github.com/theNewDynamic/gohugo-theme-ananke)主题克隆到该目录中，并将其作为Git 子模块themes添加到您的项目中。

``` cmd
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```

在配置文件中添加一行，指向当前主题。

``` cmd
echo "theme = 'ananke'" >> hugo.toml
```

启动Hugo的开发服务器来查看站点。

``` cmd
hugo server
```

按Ctrl + C可停止 Hugo 的开发服务器。

# 2.添加内容

向网站添加新页面。

``` cmd
hugo new posts/my-first-post.md
```

Hugo 在`content/posts`目录中创建了该文件，使用编辑器打开文件。

``` md
---
title: "My First Post"
date: 2022-11-20T09:03:20-08:00
draft: true
---
```

注意此处`draft`中的值为`true`。默认情况下，Hugo 在构建网站时不会发布草稿内容（draft）。

在帖子正文中添加一些内容，并把`draft`中的值为`false`。

``` md
---
title: "My First Post"
date: 2022-11-20T09:03:20-08:00
draft: true
---
## 介绍

你好世界，这是我的第一篇文章。

欢迎访问[Hugo](https://gohugo.io)官方网站!
```

保存文件，然后启动Hugo的开发服务器来查看站点。

``` cmd
hugo server
```

通过终端中显示的 URL 即可查看站点，通常为[http://localhost:1313/](http://localhost:1313/)。

# 3.配置站点

使用编辑器打开项目根目录中的站点配置文件（hugo.toml）。

``` toml
baseURL = 'http://example.org/'
languageCode = 'en-us'
title = 'My New Hugo Site'
theme = 'ananke'
```

`baseURL`修改为站点网址。

`languageCode`修改为所在的语言和区域。

`title`修改为站点标题。

根据主题设置可能需要添加`defaultContentLanguage`等配置。

启动 Hugo 的开发服务器以查看您的更改。

``` cmd
hugo server
```

至此Demo完成，我们现在可以在本地浏览器上浏览你的hugo博客。
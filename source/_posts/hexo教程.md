---
title: Hexo+GitHub Pages个人博客完全搭建详细教程
description: 使用Hexo与GitHub Pages搭建个人博客
tags:
  - hexo
  - butterfly
  - 博客
  - gh-pages
abbrlink: 2628717197
date: 2021-08-08 17:57:35
updated: 2021-08-08 17:57:35
---

## 写在前面

历时1周，在翻阅了大大小小无数的教程之后，总算是完成了个人博客的搭建。现将个人经验总结分享如下，亦做为个人存档留底。因本人才疏学浅，如有错误，欢迎在评论区指正。

{% note info simple %}
本教程使用的Hexo版本为3.8.0，不同版本差别比较大，请留意使用的版本。
{% endnote %}

**本教程默认读者已学会使用git并且拥有一个GitHub账号，如果还不会请点击TODO**

**Hexo依赖于node.js，请先安装，如需详细教程请点击TODO**

## 1 安装Hexo

### 1.1  什么是Hexo?

> Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。
>
> 引自[Hexo官网](https://hexo.io/zh-cn/docs/)

### 1.2 安装Hexo

{% note info simple %}
必须先安装Git与node.js(建议版本≥12)
{% endnote %}

在命令行窗口中输入:

```
npm install -g hexo-cli
```

稍等片刻Hexo即可安装完成，安装之后在命令行输入`hexo -v`，如果可以正常显示版本信息，即为安装成功。

## 2 配置Hexo

### 2.1 初始化博客目录

首先新建一个文件夹`myblog`(名称随意,以下统称博客目录为`myblog`)，然后在当前目录下打开命令行(Windows按住Shift右键)，输入：

```
hexo init
npm install
```

等两步安装完成后，可以看到`myblog`文件夹下包含下列文件(其他文件基本不会去修改)：

```
_config.yml    #博客配置文件
package.json   #项目配置文件
scaffolds/     #模板目录
source/        #文章目录
themes/        #主题目录
node_modules/  #插件目录
```

现在，你已经拥有了一个简单的博客站点。接下来，在命令行中输入：

```
hexo generate
hexo server
```

稍等片刻等网站渲染完成，目录下生成的`public`文件夹就是静态站点目录。在浏览器中输入`localhost:4000`，即可查看到博客页面啦(虽然Hexo自带的主题真的很丑)。

### 2.2 简单配置Hexo

然而，现在的博客实际上还是空空如也，我们需要加入个性化的内容。

打开`myblog`下的`_config.yml`文件,修改最前面的部分:

```yaml
# Site
title: #网站名称
subtitle: #网站副标题
description: #网站描述
keywords: #关键词
author: #作者
language: zh-CN #语言
timezone: 'Asia/Shanghai' #时区

# URL
## Set your site url here. For example, if you use GitHub Page, set url as 'https://username.github.io/project'
url: #你的网站的域名
```

`_config.yml`更多参数修改请参照[官方文档](https://hexo.io/zh-cn/docs/configuration)，但一般没有必要修改。

如果你想要使用别的主题，可以在网上寻找Hexo的主题自行更换。本博客使用的主题为butterfly主题，TODO

## 3  将博客同步到GitHub

{% note info simple %}
请确认已配置GitHub上的ssh key，如果没有请点击TODO
{% endnote %}


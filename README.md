

![](https://raw.githubusercontent.com/flyingwzb/flyingwzb.github.io/master/img/readme-home.png)

[![Build Status](https://travis-ci.org/flyingwzb/flyingwzb.github.io.svg?branch=master)](https://travis-ci.org/flyingwzb/flyingwzb.github.io)
[![codebeat badge](https://codebeat.co/badges/5f031df3-f6c1-4ec0-911a-ff6617ca50b9)](https://codebeat.co/projects/github-com-flyingwzb-flyingwzb-github-io-master)
[![GitHub issues](https://img.shields.io/github/issues/flyingwzb/flyingwzb.github.io.svg?style=flat)](https://github.com/flyingwzb/flyingwzb.github.io/issues)
[![License MIT](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)](https://github.com/home-assistant/home-assistant-iOS/blob/master/LICENSE)
[![](https://img.shields.io/github/stars/flyingwzb/flyingwzb.github.io.svg?style=social&label=Star)](https://github.com/flyingwzb/flyingwzb.github.io)
[![](https://img.shields.io/github/forks/flyingwzb/flyingwzb.github.io.svg?style=social&label=Fork)](https://github.com/flyingwzb/flyingwzb.github.io)


博客的搭建教程修改自 [Hux](https://github.com/Huxpro/huxpro.github.io) 
 
更为详细的教程戳这 [《利用GitHubPages快速搭建个人博客》](https://flyingwzb.github.io/2018/01/02/%E5%BF%AB%E9%80%9F%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2/) 或 [wiki](https://github.com/flyingwzb/flyingwzb.github.io/wiki/%E5%BF%AB%E9%80%9F%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2)

>
### [查看博客戳这里 👆](https://flyingwzb.github.io)



## 使用

* 开始
	* [环境](#环境)
	* [开始](#开始)
	* [撰写博文](#撰写博文)
* 组件
	* [侧边栏](#侧边栏)
	* [迷你关于我](#mini-about-me)
	* [推荐标签](#featured-tags)
	* [好友链接](#friends)
	* [HTML5 演示文档布局](#keynote-layout)
* 评论与 Google/Baidu Analytics
	* [评论](#comment)
	* [网站分析](#analytics) 
* 高级部分
	* [自定义](#customization)
	* [标题底图](#header-image)
	* [搜索展示标题-头文件](#seo-title)



### 环境

如果你安装了 [jekyll](http://jekyllcn.com/)，那你只需要在命令行输入`jekyll serve` 或 `jekyll s`就能在本地浏览器中输入`http://127.0.0.1:4000/`预览主题，对主题的修改也能实时展示（需要强刷浏览器）。



### 开始

你可以通用修改 `_config.yml`文件来轻松的开始搭建自己的博客:

```yaml
# Site settings
title: Will Wang Blog                    # 你的博客网站标题
SEOTitle: 王志彪的博客 | Will Wang Blog	 # SEO 标题
description: "Hey"	   	                 # 随便说点，描述一下

# SNS settings      
github_username: flyingwzb               # 你的github账号
jianshu_username: e71990ada2fd           # 你的简书ID。

# Build settings
# paginate: 10                           # 一页你准备放几篇文章
```

Jekyll官方网站还有很多的参数可以调，比如设置文章的链接形式...网址在这里：[Jekyll - Official Site](http://jekyllrb.com/) 中文版的在这里：[Jekyll中文](http://jekyllcn.com/).

### 撰写博文

要发表的文章一般以 **Markdown** 的格式放在这里`_posts/`，你只要看看这篇模板里的文章你就立刻明白该如何设置。

yaml 头文件长这样:

```yaml
    ---
    layout:     post
    title:      标题
    subtitle:   副标题
    date:       2017-12-31
    author:     Will Wang
    header-img: img/post-bg-article.jpg
    catalog: true
    tags:
        - 标签1
        - 标签2
    ---
```

### 侧边栏

- 看右边:
![](https://raw.githubusercontent.com/flyingwzb/flyingwzb.github.io/master/img/readme-side.png)

设置是在 `_config.yml`文件里面的`Sidebar settings`那块。

```yaml
# Sidebar settings
sidebar: true                        # 添加侧边栏
sidebar-about-description: "简单的描述一下你自己"
sidebar-avatar: /img/will-wang.jpg   # 你的大头贴，请使用绝对地址.注意：名字区分大小写！后缀名也是
```

侧边栏是响应式布局的，当屏幕尺寸小于992px的时候，侧边栏就会移动到底部。具体请见bootstrap栅格系统 <http://v3.bootcss.com/css/>

### Mini About Me

Mini-About-Me 这个模块将在你的头像下面，展示你所有的社交账号。这个也是响应式布局，当屏幕变小时候，会将其移动到页面底部，只不过会稍微有点小变化，具体请看代码。

### Featured Tags

看到这个网站 [Medium](http://medium.com) 的推荐标签非常的炫酷，所以我将他加了进来。
这个模块现在是独立的，可以呈现在所有页面，包括主页和发表的每一篇文章标题的头上。

```yaml
# Featured Tags
featured-tags: true  
featured-condition-size: 1     # A tag will be featured if the size of it is more than this condition value
```

唯一需要注意的是`featured-condition-size`: 如果一个标签的 SIZE，也就是使用该标签的文章数大于上面设定的条件值，这个标签就会在首页上被推荐。
 
内部有一个条件模板 `{% if tag[1].size > {{site.featured-condition-size}} %}` 是用来做筛选过滤的.

### Social-media Account

在下面输入的社交账号，没有的添加的不会显示在侧边框中。新加入了[简书](https:/www.jianshu.com)链接, <http://www.jianshu.com/u/e71990ada2fd>

	# SNS settings
	RSS: false
	jianshu_username: 	jianshu_id 
	zhihu_username:     username
	facebook_username:  username
	github_username:    username
	# weibo_username:   username
	
	

![](http://ww4.sinaimg.cn/large/006tKfTcgy1fgrgbgf77aj308i02v748.jpg)

### Friends

好友链接部分。这会在全部页面显示。

设置是在 `_config.yml`文件里面的`Friends`那块，自己加吧。

```yaml
# Friends
friends: [
    {
        title: "Will Wang Blog",
        href: "https://flyingwzb.github.io/"
    },
    {
        title: "Apple",
        href: "https://apple.com/"
    }
]
```


### Keynote Layout

HTML5幻灯片的排版：

![](https://camo.githubusercontent.com/f30347a118171820b46befdf77e7b7c53a5641a9/687474703a2f2f6875616e677875616e2e6d652f696d672f626c6f672d6b65796e6f74652e6a7067)

这部分是用于占用html格式的幻灯片的，一般用到的是 Reveal.js, Impress.js, Slides, Prezi 等等.我认为一个现代化的博客怎么能少了放html幻灯的功能呢~

其主要原理是添加一个 `iframe`，在里面加入外部链接。你可以直接写到头文件里面去，详情请见下面的yaml头文件的写法。

```yaml
    ---
    layout:     keynote
    iframe:     "http://huangxuan.me/js-module-7day/"
    ---
```

iframe在不同的设备中，将会自动的调整大小。保留内边距是为了让手机用户可以向下滑动，以及添加更多的内容。


### Comment

博客不仅支持 [Disqus](http://disqus.com) 评论系统,还加入了 [Gitalk](https://gitalk.github.io/) 评论系统，[支持 Markdwon 语法](https://guides.github.com/features/mastering-markdown/)，cool~

#### Disqus

优点：国际比较流行，界面也很大气、简洁，如果有人评论，还能实时通知，直接回复通知的邮件就行了；

缺点：评论必须要去注册一个disqus账号，分享一般只有Facebook和Twitter，另外在墙内加载速度略慢了一点。想要知道长啥样，可以看以前的版本点[这里](http://brucezhaor.github.io/about.html) 最下面就可以看到。

> Node：有很多人反映 Disqus 插件加载不出来，可能墙又架高了，有条件的话翻个墙就好了~

**使用：**

**首先**，你需要去注册一个Disqus帐号。**不要直接使用我的啊！**

**其次**，你只需要在下面的 yaml 头文件中设置一下就可以了。

```yaml
# 评论系统
# Disqus（https://disqus.com/）
disqus_username: flyingwzb
```

#### Gitalk

优点：界面干净简洁，利用 Github issue API 做的评论插件，使用 Github 帐号进行登录和评论，最喜欢的支持 Markdown 语法，对于程序员来说真是太 cool 了。

缺点：配置比较繁琐，每篇文章的评论都需要初始化。

**使用：**

参考我的这篇文章：[《为博客添加 Gitalk 评论插件》](https://flyingwzb.github.io/2018/01/04/%E4%B8%BA%E5%8D%9A%E5%AE%A2%E6%B7%BB%E5%8A%A0Gitalk%E8%AF%84%E8%AE%BA%E6%8F%92%E4%BB%B6/)


### Analytics

网站分析，现在支持百度统计和Google Analytics。需要去官方网站注册一下，然后将返回的code贴在下面：

```
# Baidu Analytics
ba_track_id: 4cc1f2d8f3067386cc5cdb626a202900

# Google Analytics
ga_track_id: 'UA-49627206-1'            # 你用Google账号去注册一个就会给你一个这样的id
ga_domain: huangxuan.me			# 默认的是 auto, 这里我是自定义了的域名，你如果没有自己的域名，需要改成auto。
```

### 统计网站PV、UV

新增网站访问量的PV、UV统计，采用[不蒜子](http://ibruce.info/2015/04/04/busuanzi/)提供的js，动态引入即可实现统计功能。

在`footer.html`文件中加入引入相关配置
![](https://github.com/flyingwzb/flyingwzb.github.io/blob/master/img/blog/blog-022.png?raw=true)

统计网站PV、UV统计效果如下：
![](https://github.com/flyingwzb/flyingwzb.github.io/blob/master/img/blog/blog-023.png?raw=true)


### JS实现文章打赏功能

在js包路径下引入`ds.js`文件，并在`post.html`文件如加入如下配置：
```javascript 1.8
// 引入ds.js源文件
<script src='{{ "/js/ds.js" | prepend: site.baseurl }}'></script>
<script>
    new tctip({
        // 按钮UI位置
        top: '20%',
        button: {
            // id对应颜色配置
            id: 6,
            // 可选打赏或赞助两种类型，其他类型不可用
            type: 'dashang'
        },
        list: [
            {
                type: 'alipay',
                // 支付宝付款码，这里可以将照片转成base64码，加载更快
                qrImg: 'data:image/jpeg;base64,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'
            }, {
                type: 'wechat',
                // 微信付款码，这里可以将照片转成base64码，加载更快
                qrImg: 'data:image/jpeg;base64,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'
            }
        ]
    }).init()
</script>
```

刷新页面，点击博客的每一篇文章即可看到我的博客打赏码（喜欢请打赏），如下：
![](https://github.com/flyingwzb/flyingwzb.github.io/blob/master/img/blog/blog-024.png?raw=true)

### Customization

如果你喜欢折腾，你可以去自定义这个模板的 Code。

**如果你可以理解 `_include/` 和 `_layouts/`文件夹下的代码（这里是整个界面布局的地方），你就可以使用 Jekyll 使用的模版引擎 [Liquid](https://github.com/Shopify/liquid/wiki)的语法直接修改/添加代码，来进行更有创意的自定义界面啦！**

### Header Image

博客每页的标题底图是可以自己选的，看看几篇示例post你就知道如何设置了。
  
标题底图的选取完全是看个人的审美了。每一篇文章可以有不同的底图，你想放什么就放什么，最后宽度要够，大小不要太大，否则加载慢啊。

> 上传的图片最好先压缩，这里推荐 imageOptim 图片压缩软件，让你的博客起飞。

但是需要注意的是本模板的标题是**白色**的，所以背景色要设置为**灰色**或者**黑色**，总之深色系就对了。当然你还可以自定义修改字体颜色，总之，用github pages就是可以完全的个性定制自己的博客。

### SEO Title

我的博客标题是 **“Will Wang Blog”** 但是我想要在搜索的时候显示 **“王志彪的博客 | Will Wang Blog”** ，这个就需要 SEO Title 来定义了。

其实这个 SEO Title 就是定义了<head><title>标题</title></head>这个里面的东西和多说分享的标题，你可以自行修改的。

### 关于收到"Page Build Warning"的 Email

由于jekyll升级到3.0.x,对原来的 pygments 代码高亮不再支持，现只支持一种-rouge，所以你需要在 `_config.yml`文件中修改`highlighter: rouge`.另外还需要在`_config.yml`文件中加上`gems: [jekyll-paginate]`.

同时,你需要更新你的本地 jekyll 环境.

使用`jekyll server`的同学需要这样：

1. `gem update jekyll` # 更新jekyll
2. `gem update github-pages` #更新依赖的包

使用`bundle exec jekyll server`的同学在更新 jekyll 后，需要输入`bundle update`来更新依赖的包.

> Note：
> 可以使用 `jekyll -s` 命令在本地实时配置博客，提高效率。详见 [Jekyll.com](http://jekyllcn.com/)

参考文档：[using jekyll with pages](https://help.github.com/articles/using-jekyll-with-pages/) & [Upgrading from 2.x to 3.x](http://jekyllrb.com/docs/upgrading/2-to-3/)


## 致谢

1. 这个模板是从这里 [Hux](https://github.com/Huxpro/huxpro.github.io) fork 的, 感谢这个作者。 
2. 感谢 Jekyll、Github Pages 和 Bootstrap!

[回到顶部](#readme)	

## License

遵循 MIT 许可证。有关详细,请参阅 [LICENSE](https://github.com/flyingwzb/flyingwzb.github.io/blob/master/LICENSE)。




---
layout: post
title:  "Jekyll入门教程"
date:   2020-07-23 19:37:00 +0800
categories: chinese
---
Jekyll是一个简洁、轻量级的博客、静态网站生成工具。今天我们来学习一下它的用法。

我使用的是macOS。使用macOS内置的`/usr/bin/ruby`可能会产生一些问题，我们最好还是用homebrew安装一个新的ruby。

    brew install ruby

新ruby的位置是`/usr/local/opt/ruby/bin/ruby`。

我们在`.bash_profile`中加入这两行

    export PATH="/usr/local/opt/ruby/bin:$PATH"
    export PATH="/usr/local/lib/ruby/gems/2.7.0/bin:$PATH"

然后`source .bash_profile`，环境变量就配置好了。

我们可以通过

    which ruby
    which gem

来确认这一点。

接下来

    gem install jekyll bundle
    jekyll new myblog
    cd myblog

我们的博客就设置好了。

要在本地运行博客，只需要

    bundle exec jekyll serve

我们就可以通过`localhost:4000`访问我们的博客了。

接下来我们可以修改`_config.yml`中的个人信息，编辑`about.markdown`来修改About页面。
如果要撰写新博文的话，在`_posts`文件夹里创建一个新的Markdown文档就可以了。

是不是很简单呢？
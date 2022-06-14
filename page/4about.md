---
layout: page
title: 关于
permalink: /about/
icon: heart
type: page
---
* content
  {:toc}


## 个人简介

我是清阳，网名conge。

这是我的weblog。内容上，目前主要写跑步，育儿周记和习惯养成。最近在关注冥想。

目前每周更文二到四篇，请通过 RSS阅读器 订阅更新：https://conge.github.io/feed.xml。

## 建站缘由

我是conge，从2014年开始，在简书上写博客，一直写到2020年9月。最终，决定离开。

原因是简书是一个中国国内的网站，经常会因为自我审查，就把我的文章给隐藏。

而我，是一个不关心政治，不谈论政治，只是写文章记录一些自己读过的书，跑过的风景，养孩子踩过的坑。如此的文章也能被动不动封禁，我就看不懂了。而且，jianshuo.com也不止一次的在政治敏感时期，比如两会时，禁止发文。这对于需要持续书写的人来说，很不方便。

另外，自己的写作，从一开始的写给别人看，变成了写给自己的周记。也不靠这个吃饭，也不担心有没有人阅读。选择在Jianshu.com上写，一开始纯粹是因为他的编辑器好用，不用自己找图床。但现在，越来越觉得，自己写的东西，在自己手上留一份儿比较好。与其用别人的，不如用自己的。

一开始，考虑过在Google Cloud或者其他云服务商找个free tier的主机搭个Wordpress就完了，但实在不想折腾。考察了一遍，干脆就用Jekyll和Github搭建个完了。<del>也先不开评论</del>，也不折腾美观如何。先把自己在jianshu.com上的文章转过来再说。

遂有此站。

自 2019 年 09 月 19 日起，本站已运行 <span id="days"></span> 天，截至 {{ site.time | date: "%Y 年 %m 月 %d 日" }}，写了博文 {{ site.posts.size }} 篇，{% assign count = 0 %}{% for post in site.posts %}{% assign single_count = post.content | strip_html | strip_newlines | remove: ' ' | size %}{% assign count = count | plus: single_count %}{% endfor %}{% if count > 10000 %}{{ count | divided_by: 10000 }} 万 {{ count | modulo: 10000 }}{% else %}{{ count }}{% endif %} 字。

## 感谢

从简书到Jekyll文章的转换，我使用了Lework的一个Python script（[文章链接](https://lework.github.io/2019/06/15/jianshu-to-jekyll/)）。

这个script把我在简书的800多篇文章给批量转换了一些。转换过程有400多篇成功。剩下的400多篇，只是没有找到发表日期等信息，没能完美转换。但是文章的内容都转换的很好，所有的相关图片也都拉到了本地。有了这些个底子，我应该可以尽快的把所有的文章都修改好。

Lework帮了我的大忙，在这里鸣谢一下。没有他的的script，我大概还会忍受jianshu.com一阵子。

## 联系我

* [Twitter](https://twitter.com/conge)
* [Facebook](https://www.facebook.com/psychattic)
* [linkedin](https://www.linkedin.com/in/qingyang-li/)
* [v2ex](https://www.v2ex.com/member/conge)
* [Github](https://GitHub.com/conge)
* [豆瓣](https://www.douban.com/people/conge/)
* [Seattle, WA, US](http://www.google.com/maps?q=Seattle,%20WA,%20USA)

## 捐赠

若您觉得本博客所创造的内容对您有所帮助，可考虑略表心意，支持一下。

{% include reward.html %}

## 本页历史

```
2020-09-19 created
2022-04-22 增加站点状态，页面历史，赞赏
```

{% include comments.html %}

<script>
var days = 0, daysMax = Math.floor((Date.now() / 1000 - {{ "2019-09-19" | date: "%s" }}) / (60 * 60 * 24));
(function daysCount(){
    if(days > daysMax){
        document.getElementById('days').innerHTML = daysMax;
        return;
    } else {
        document.getElementById('days').innerHTML = days;
        days += 10;
        setTimeout(daysCount, 1);
    }
})();
</script>

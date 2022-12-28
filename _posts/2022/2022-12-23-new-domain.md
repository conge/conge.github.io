---
layout: post
title: "启用新域名"
date: "2022-12-23 16:55:45"
categories: 隨筆
auth: conge
tags: 网络 网站 本站公告
---
* content
{:toc}

给网站换了个新域名, [conge.livingwithfcs.org](https://conge.livingwithfcs.org).

换域名这种小事儿，原本不值得一说。但之所以要换，乃是因为A4纸事件造成的国内网络收紧。这篇文章，作为A4纸事件的余波，自有其意义。





## 起因

我的小博客，写完了，主要是在朋友圈甩个链接，给关心的人来看看。毕竟文章都太个人了，其作用有限。我的亲朋好友或许有兴趣读读。再者，就是如果能在我年老偶尔重读时，能勾起自己的些许温馨回忆，便是锦上添花了。

用Google监测网站的浏览量，完全是出于惯性。其实自己并不知道那些监测对我会有什么用处。至少我写博客这么多年，从来没有根据访问量做过什么调整。

没想到，这几天，我用到了监测。下图中是Google Analycis给我的提醒，说我的网站从从11月27日开始，出现了用户数量、网站阅读量和页面阅读量都出现了异常的下降。其中，用户数从预计的300左右降至不足100，阅读量从700左右降到200多。

![2022-12-23-insights.png](https://s2.loli.net/2022/12/24/HCFlmpTGfz8Zi6Y.png)

我想了想，应该是11月26日国内各地的突发事件，引起了国内网监部门对于外网的收紧，造成了国内访问我在github托管的博客的被墙。

随后，猜想被证实，我妹说我发的文章链接打不开。

但是，在同一个城市的我弟说，可以打开。

关于这个，我有诸多猜想。也许我弟翻墙了吧。或者是因为他住在郊区而我妹妹在市区的原因？或者是用的是不同的网络运营商的服务。

不过，我也懒得深究，究查出来，我也没有什么办法解决不是吗？还是想办法，做自己能控制的事儿吧。

## 换域名

我能做的，也就是试试换域名了。

我手头有一个域名，是我给自己的公益组织 [FCS Foundation](https://livingwithfcs.org) 做网站用的，叫做 livingwithfcs.org。我把自己的id放到前面，叫做Conge.livingwithFCS.org，挺好，就是Conge带着FCS生活的意思。拿来描述博客，一点儿也不违和。

换域名的步骤是这样：

1. 到自己的 github repo 的 Setting 下面的Pages，找到`Custom domain`部分,在文本框里填入自己的自定义域名`conge.livingwithfcs.org`,之后点击`Save`保存。这一步实际上会在Repo中增加个`CNAME`的文本文件。
2. 到自己的域名托管商网站里更改DNS设置。我用的是Google Domains 托管自己的域名。在DNS记录管理那里，添加新记录，类型为CNAME，把记录命设为`conge.livingwithfcs.org`，记录值设置为Github repo原来的域名，对我来说就是 `conge.github.io`。
3. 第2步完成之后，回到 1 的页面，完成域名的自动检查之后，勾选`Enforce HTTPS`，然后就是等上一会儿，设置生效，就可以用启用新的域名了。

这几步设置完了之后，就可以 [https://conge.livingwithfcs.org](https://conge.livingwithfcs.org) 的域名来访问我的博客了。而且，之前的 ”[https://conge.github.io](https://conge.github.io)"的域名也会自动跳转到新域名。

## 效果

更换域名之后，我在网站上下左右试了试，都还行。多数链接已经自动更改了。[running page](https://conge.livingwithfcs.org/running_page/) 似乎需要重新改一下某些链接，不过问题也不大，有空再做。

因为老域名并没有失效且可以自动跳转，我也不用担心之前的文章链接失效的问题。

在朋友圈发了个测试链接。到目前位置，得到的反馈都是没有问题。那就好啦，先这样吧。

希望我的RSS订阅读者，不会收到什么影响吧。

2022-12-28， 补充，换了域名之后，果然访问就没有问题了。朋友圈好几个朋友做了测试。而且，Google Analytics的数据也有所反应， 如下：

![2022-12-23-result.png](https://s2.loli.net/2022/12/29/M1lg2HhtiKmBrQA.png)

```
2022-12-23 初稿
2022-12-18 补充效果。
```

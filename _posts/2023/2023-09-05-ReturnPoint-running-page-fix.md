---
layout: post
title: "折返点 2335 - 修复跑步页面的故障"
date: "2023-09-05 10:49:31"
categories: 折返点
auth: conge
tags: 跑步 
---
* content
{:toc}

![](https://raw.githubusercontent.com/shaonianche/gallery/master/running_page/running_page_logo.png)

我有个一 [跑步页面](https://conge.livingwithfcs.org/running_page/)，是基于 [@yihong0618](https://github.com/yihong0618/gitblog) 的开源项目 [running_page](https://github.com/yihong0618/running_page) 通过 Github Actions 自动同步我的跑步数据，自动生成的。最近这个工作流忽然报错，说部署过程超时了。

本文记录一下这个错误以及修复过程。对了，我借着这次折腾的机会，给妻子的跑步也做了个数据页面，[按此处查看](https://conge.livingwithfcs.org/freya_running/)。




## 工作流

我的 [跑步页面](https://conge.livingwithfcs.org/running_page/) 生成的整个工作流是这样的：

1. 数据产生与共享：我通过 Garmin 手表记录自己的跑步。跑步完成后，数据会记录在 Garmin App 里，并且同步共享到 Starva。
2. 数据更新：通过托管在 Github 的我的 [Running page](https://github.com/conge/running_page/) 项目的`Run Data Sync` workflow 从 Strava 同步数据到跑步页面项目。
3. 页面构建与部署：如果有新数据， `Run Data Sync` 会触发启动 `pages-build-demployment` workflow，去创建并且部署新页面到 [Running page](https://github.com/conge/running_page/) 的`gh-pages` 分支。

以上步骤，1 会在我每次跑步之后完成。2 和 3 则的数据更新和是每天自动运行一次。

如果一切顺利，我的 [跑步页面](https://conge.livingwithfcs.org/running_page/) 就会更新到最新数据。如果第 2，3 步失败，我会收到邮件提醒。

## 问题

我从今年三月份第一次收到报错邮件，提示我 pages build and deployment 步骤失败。之后，同样的邮件，之后每个月大概会收到一次。

到了七月下旬，我收到报错邮件的频率开始提升。到了 8 月份，我更是收到了 8 次报错。

一开始我并没有在意，因为我知道，只要`Run Data Sync` 到数据更新没有问题，偶尔的页面构建失败没什么问题。只要页面更新步数成功一次，就会把页面带到最近的数据。

而且，除了利用 App 自动记录和更新数据，我自己有手动记录的习惯，数据都放在 [我跑步手动记录 github repo](https://github.com/conge/RunningStreak)。

但越来越频繁的报错也实在是烦，于是我决定还是看一看。

![2023-09-05-github-01.png](https://s2.loli.net/2023/09/06/NATOXbxmQ3wHVWU.png)

## 诊断

我从 email 的链接进去，查看失败的工作流日志，马上就意识到了问题的所在：

1. 我的生成的 gh-pages 居然有 5.4GB 之巨
2. 巨大的文件造成整个 `pages-build-demployment` 需要 38 分钟多，且因为超时而失败。

为了查看这是不是个普遍问题，我按图索骥，找了其他几个用户 run page 项目，发现同样的工作流，别人都是两分钟内就完事儿，很多都还不到一分钟。而且，他们的文件大小只有几十或者一百多 MB，比我的要小很多。

我再次查看自己的日志，发现每次的部署更新，都会产生一些新文件，文件名类似于

```
e73e9428-0a91a86e97332d73eebc.js
e73e9428-0a91a86e97332d73eebc.js.map
425-1e1d4f0b9bbff1b9abc8.js.map
425-1e1d4f0b9bbff1b9abc8.js.
webpack-runtime-6af4f18872332333e62f.js
webpack-runtime-6af4f18872332333e62f.js.map
webpack.stats.json
```

这写文件大小不等，合起来也有 20 多 MB，这应该是 gh-pages 分支变大的原因。我大概我的 gh-pages 分支，发现里面文件数巨大，且都是 `js.map` 和 `js` 文件。这些文件就应该是罪魁了。

## 求助

这实在是很奇怪，但我也不知道怎么办，于是就在 [running_page](https://github.com/yihong0618/running_page) 的讨论页面提问。yihong0618 很快回复，认同是“gh-pages 这个分支太大”，并建议“删掉这个分支，都重新弄试试”。

## 修复

我按照 yihong0618 的建议操作，问题已经解决。

解决步骤：

1. 删除 gh-pages 分支
2. 到 `Actions -> Workflows -> All Workflows` 中，重新跑一次 `Publish GitHub Pages` 生成新的的 `gh-pages` 分支。
3. 之后 `pages build and deployment` workflow 会被自动触发。

最终的结果，`pages build and deployment` 从之前的需要 38 分钟，变成了只需要 38 秒完成。分支大小也从 5.4 GB 变成了只有 14.5MB。变化巨大呀。

## 探讨

### 文件变大

虽然问题得到了解决，但是 `gh-pages` “日积月累为啥会这么大啊” 却仍没有答案。

我排查了一下 build+deployment 那个 workflow 的日志， 发现随着时间的推移，artifacts 的大小是越来大，running time 从一开始的只有几分钟，用了一年的时间慢慢的越来越长，一直到现在的 30 几分钟，部署超过 10 分钟的限制，出现 timeout 错误。

分支变大的原因，很可能是我每次有新的跑步，就会生成几个 `.js`, `.js.map` 文件，而这些文件大小合计约 20 多 MB。

如果按照一年跑 360 次，每次产生 20MB 新文件估算，一年产生的文件大概会有 20MB*360=7.2GB 之巨呀。

而且，看样子，如果放任不管，`gh-pages` 几乎是不可避免的会一直变大。比如，自从问题修复后，我的整个 workflow 运行了两次了。第二次运行之后，我的`gh-pages` 已经从 [14.5MB](https://github.com/conge/running_page/actions/runs/3441733805) 变成 [15.9MB](https://github.com/conge/running_page/actions/runs/6078925422) 了。

### 应对策略

从我删除 gh-pages 重新 build 就能瘦身，且不影响页面功能这一点来看，完全可以每次 build 的时候将先前生成的 `.js`, `.js.map` 文件进行删除或者覆盖。

甚至，可以先完全删除整个 `gh-pages` 分支，再重新生成也是可以接受的，这样就能保证页面一直“最小”。

这样看来，我上面修复问题的步骤，应该成为这个项目更新页面的步骤，也就是在每次重新部署之前，先删除`gh-pages` 再重新生成。

以上。

## 广而告之： FCS 基金会 线上五公里义跑

我已经报名了 [FCS 基金会 线上五公里义跑](https://livingwithfcs.networkforgood.com/)，等烟雾散去，就抓紧跑几次变速跑，给比赛做作训练。看看今年还能不能在 19 分钟以下完成 5 公里吧。

欢迎报名 [FCS 基金会 线上五公里义跑](https://livingwithfcs.networkforgood.com/)

![5K_2023.jpeg](https://s2.loli.net/2023/08/15/iSFnUlg7BevjfPD.jpg)

### 你能如何参与

如果你也愿意支持这次义跑，你可以：

1. 帮我转发这篇文章。越多的人看到这篇文章越好，我相信您的转发会帮到我。
2. 在 9 月的比赛周，陪我跑个五公里。
3. 捐赠： [报名链接](https://livingwithfcs.networkforgood.com/) 有捐款选项。或者通过本文的打赏链接也可以捐款。

感恩！

## Running log

| week 35, 2023 |
| :-----------: |
| ![2023_week35.png](https://s2.loli.net/2023/09/06/KJXAuFvNZ6c4MyD.png) |

## 折返点

| Date     | Pics  |
| :------- | :------------------------------------------------------------------: |
| 20230827 | ![20230827.jpeg](https://s2.loli.net/2023/09/06/VZ1dv2oMLE8NzgQ.jpg) |
| 20230828 | ![20230828.jpeg](https://s2.loli.net/2023/09/06/ajsN3XOuiSDt8HU.jpg) |
| 20230829 | ![20230829.jpeg](https://s2.loli.net/2023/09/06/5BM7FxRzOhuEg4m.jpg) |
| 20230830 |缺|
| 20230831 | ![20230831.jpeg](https://s2.loli.net/2023/09/06/dhIYsjW8nHSTBJN.jpg) |
| 20230901 | ![20230901.jpeg](https://s2.loli.net/2023/09/06/Pn6qsyMCUNvdY8W.jpg) |
| 20230902 | ![20230902.jpeg](https://s2.loli.net/2023/09/06/LEvyMB8lVzY24Op.jpg) |

## 我的更多跑步数据展示

* [我的跑步主页](https://conge.livingwithfcs.org/running_page/)
* [我跑步手动记录 github repo](https://github.com/conge/RunningStreak)
* [我的 Strava 页面](https://www.strava.com/athletes/57680242)

```
2023-09-05 初稿
```

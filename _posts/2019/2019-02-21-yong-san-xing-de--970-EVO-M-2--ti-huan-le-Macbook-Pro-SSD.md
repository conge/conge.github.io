---
layout: post
title: "用三星的 970 EVO M.2 替换了Macbook Pro SSD"
date: "2019-02-21 13:54:30"
categories: 隨筆
excerpt: "我的Macbook Pro (MBP)，是2014年10月份在Ebay买的，型号是MacBook Pro (Retina, 13-inch, M..."
auth: conge
---
* content
{:toc}

我的Macbook Pro (MBP)，是2014年10月份在Ebay买的，型号是MacBook Pro (Retina, 13-inch, Mid 2014)。
![ ](/assets/images/隨筆/118382-ac51f02017eea09d.png)

当时我在Oswego，没有工作，准备自学个计算机的学位，转行。当时，我得到了Georgia Tech的OMSCS录取，但却没有自己的笔记本电脑。虽然家里有一台台式机可用，但我还是想要一台便携但笔记本电脑，可以带到图书馆，咖啡馆，移动学习。当时Ebay上正好遇到一个商家打折卖全新的MBP，于是心动，下单。

当时下定的决心是，既然决定买电脑是因为要完成硕士课程，那么，就一定要拿到学位。这个目标有望今年达成。

当时这款MBP不属于高配置版本。内存大小8GB，可用。硬盘为128GB SSD。CPU是2.6 GHz Intel Core i5。

四年多了，8GB内存勉强够用，但是128GB容量的硬盘，却往往让捉襟见肘。学编程的过程，需要装各种软件，开发框架，IDE，虚拟系统。128GB一下子就见底儿了。为了安装这些Xcode，我不得不先卸载一些Mac系统自带的大块头软件，比如办公系列的Keynote，把大量的文件放到云端，用的时候才下载，用完再传回。浪费时间。

即便如此，我还是常常要面对硬盘不够用的窘境。

常常查询硬盘升级方案，当时的方案倒是有，[Transcend](https://www.transcend-info.com/apple/)提供了内置外置的方案，但是价格很贵。后来出现了一家叫做 Other World Computing [（OWC）](https://eshop.macsales.com/shop/ssd/owc)
  的公司，也提供MBP的SSD升级方案，价格比Transcend稍微便宜一些，但是对我来说还是贵。

以上两家的产品价格昂贵，大概是因为它们都是专门针对Apple电脑提供解决方案。

而SSD硬盘的大厂出的产品，因为接口问题，不能直接用到Apple电脑上。从2018年以来，SSD硬盘价格一路走低，但是Transcend和OWC的产品价格坚挺。当时400美元能买到约256GB的Transcend或OWC生产的硬盘。同样的钱，能买到512的三星或者Intel的SSD了。

时间来到2018年底，突然发现1 TB的SSD已经快降到200美元了，又发现，网上已经有了针对2014年MBP使用普通NVMe SSD的升级MBP的方案了。

在做了相关研究后，我在黑五的时候，下单买了一块三星的SSD， 具体型号为Samsung 970 EVO M.2 NVMe 1TB。同时买了拆MBP后盖儿的工具和普通NVMe SSD到MBP的转接口。

转接口是整个方案的关键，不要买错了。我的MPB是2014年的，所以用的是Sintech NGFF M.2 nVME SSD Adapter Card for Upgrade 2013-2015 Year Macs （[Amazon 链接](https://www.amazon.com/Sintech-Adapter-Upgrade-2013-2015-MacBook/dp/B01CWWAENG)），制造商在中国。
![Sintech](/assets/images/隨筆/118382-9607111102505fa8.png)


硬盘我以税前200刀出头的价格拿到，到手是228美元。这款目前售价是税前250美元。11月份黒五下的单，1月份才拿到产品，三星估计是给我新做的硬盘。

这个周末，我终于有时间，升级了一下自己的MacBook Pro，把它的硬盘容量，从128GB提升到了1TB。

![ ](/assets/images/隨筆/118382-64f54fb9b4c42625.png)

-----

升级步骤，我不详细写了，网上的方案已经非常详细了。我是参考了下面的两个方案，最终使用的方案二步骤。但是方案一有详细的拆MBP后盖儿的方法，也一定要看。

二者的区别，就在于方案一需要制作一个MacOS的系统安装U盘，以应对可能发生的MBP不能识别你的硬盘的问题（我没有遇到这个问题）。方案二应对这个问题的办法，是制作一个Ubuntu的安装U盘。

比较而言，制作Ubuntu的安装盘，操作简单，而且只需要一个2GB大小的U盘。制作MacOS的安装盘，虽说也不难，但是需要你的MBP至少还有10几GB的空间，因为过程中要下载一个8GB的文件，且需要至少8GB的U盘制作安装盘，操作过程也相对麻烦（但并没有多难，参见下面的方案一）。

⚠️__注意__：

1. 方案二操作过程中又一个坑，那就是用`CMD-ALT-R`键进入恢复模式的时候，有可能遇到2003F错误。遇到这个错误不要慌张，这多半儿是Mac没找到Wifi的原因。你就不停的重来就行了。我是在第四次的时候，才得以进入恢复模式的。
![2003F error](/assets/images/隨筆/118382-f0d84e5525a27bd2.png)
2. 如果你也有需要做相同操作，建议先看方案一中的视频，该视频非常详细，按照它不会出错。之后再看方案二，对比一下异同。如果你要使用方案二，也一定要再熟悉了方案一的情况下再做操作。
3. 换硬盘前，建议升级到最新的系统。如此，上面提到安装U盘，无论是Ubuntu和macOS 的，有可能用不着。我就没有用到。__但是__，即便用不着，也一定要做，不然万一需要你却没有，你还得返回头去做。做Ubuntu的简单，随便借一台电脑就可以做。但是做macOS的安装盘，你则需要借一台Mac。
4. 如果你有两个U盘，不妨UBUNTU安装盘和MacOS安装盘各做一个，这样两个方案都可用。在恢复系统时候，优先使用方案二。如果实在过不去上面提到的那个“2003F”错误，再使用方案一中的MacOS安装盘，直接装个新系统，完事儿之后在通过Time Machine恢复你先前的系统就好了。
5. 如果你的机型是2013和2014版本的，你可能会出现开机慢，深度睡眠后不能唤醒而必须重启和散热的问题，解决方案可以看[这篇文章](https://www.v2ex.com/t/482777)，基本上，这个问题目前无解。而且这个问题不只是这个硬盘有，Apple自己的Nvme硬盘也有同样的问题。如果Apple不提供底层驱动的解决方案，大概不能解决了。给用户剩下的选项，只有养成新的使用习惯了，那就是每次使用完毕，要么不要睡眠，要么关机。非常不方便。如果不喜欢，只能换回自己的小硬盘了。


----

下面是我参考的两个方案。你需要懂英语且会翻墙。

方案一 From [Youtube](https://www.youtube.com/watch?v=NU6yatTvyyk&t=291s)

方案二 from [medium.com](https://medium.com/@vsulak.svk/how-to-replace-macbook-ssd-with-samsung-970-evo-m-2-nvme-on-macos-mojave-945684e79daa)


```
2019-02-17
```

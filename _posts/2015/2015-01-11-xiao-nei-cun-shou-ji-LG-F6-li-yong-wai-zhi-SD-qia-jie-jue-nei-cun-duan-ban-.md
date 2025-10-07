---
layout: post
title: "小内存手机LG F6利用外置SD卡解决内存短板"
date: "2015-01-11 12:41:55"
categories: 隨筆
excerpt: "本文主体翻译自 Sean Chen的文章 http://kingoftweaks.blogspot.com/2014/11/lg-f6.html..."
auth: conge
---
* content
{:toc}

> 本文主体翻译自 Sean Chen的文章 <http://kingoftweaks.blogspot.com/2014/11/lg-f6.html>。 在原文基础上增加部分内容。

LG F6是一款Android手机，各方面性能都不错，只是内存比较小，是短板。这篇文章目的是利用外置SD卡解决这个问题。

![LG F6. Photo credit: Evleaks](http://i1-news.softpedia-static.com/images/news2/LG-Optimus-F6-for-MetroPCS-Leaks-387081-3.jpg)

1.首先，看看手机里有没有下面这个APP

![](/assets/images/隨筆/118382-81fda12fb2e016ff.png))

没有的话，进行下面这步获取root权限，有的话，则说明已经root过了，跳过这一步，去下一步。

> 下载安装 TowelRoot_v1.apk (<http://yun.baidu.com/share/link?shareid=975915991&uk=3996418174&fid=907551448668921>), 然后马上下载安装 eu.chainfire.supersu.apk (<http://yun.baidu.com/share/link?shareid=648356771&uk=536992520&fid=906343825986736>)。

2.这篇文章的末尾有一个列表，列举了手机上的可以删掉的软件。把它们都删除了即可。不要删错了。删除方法请参考这篇文章<http://www.dashi.com/guide/article/id/1288.html>

3.用 FolderMount 这个软件把一些比较大的文件夹挂载到外置SD卡上去 ( DCIM,  Tencent，Weixin之类的)。 下载地址  <http://down.tech.sina.com.cn/3gsoft/download.php?id=11394>。使用方法参考这篇文章 <http://bbs.xiaomi.cn/thread-10964367-1-1.html>。

4.如果空间还是不够的话，可能需要App2SD or Link2SD. 这个操作比较复杂，回头再写。

----

可删除文件列表：

AAT.apk
ApplicationManagerbin.apk
ApplicationManagerbin.odex
Books.apk
Books.odex
CABLService.apk
CABLService.odex
ChromeBookmarksSyncAdapter.apk
ChromeBookmarksSyncAdapter.odex
ChromeWithBrowser.apk
ChromeWithBrowser.odex
DmfAdmin.apk
DmfAdmin.odex
EasySettings.apk
EasySettings.odex
ECID-release.apk
ECID-release.odex
GoogleBackupTransport.apk
GoogleBackupTransport.odex
GoogleCalendarSyncAdapter.apk
GoogleCalendarSyncAdapter.odex
GoogleContactsSyncAdapter.apk
GoogleContactsSyncAdapter.odex
GoogleDrive.apk
GoogleDrive.odex
GoogleFeedback.apk
GoogleFeedback.odex
Hangouts.apk
Hangouts.odex
LGBackupbin.apk
LGBackupbin.odex
LGBrowser_JB.apk
LGBrowser_JB.odex
LGEIMEbin.apk
LGEIMEbin.odex
LGEmailbin.apk
LGEmailbin.odex
LGQRemote.apk
LGQRemote.odex
LGSearchWidgetProvider.apk
LGSearchWidgetProvider.odex
LGSetupWizard_JB.apk
LGSetupWizard_JB.odex
LGSetupWizardApp.apk
LGSetupWizardApp.odex
Magazines.apk
Magazines.odex
Memobin.apk
Memobin.odex
MemoWidgetbin.apk
MemoWidgetbin.odex
MLT.apk
MLT.odex
MusicWidgetbin.apk
MusicWidgetbin.odex
MyMetro.apk
MyMetro.odex
Phonesky.apk
Phonesky.odex
PhotoAlbumWidgetbin.apk
PhotoAlbumWidgetbin.odex
PlayGames.apk
PlayGames.odex
PlusOne.apk
PlusOne.odex
QMemobin.apk
QMemobin.odex
QuickSet.apk
QuickSet.odex
QuicksetSDK.apk
QuicksetSDK.odex
SetupWizard.apk
SetupWizard.odex
SmartShare.apk
SmartShare.odex
SmartShareProvider.apk
SmartShareProvider.odex
StreamingPlayerbin.apk
StreamingPlayerbin.odex
Street.apk
Street.odex
TagGoogle.apk
TagGoogle.odex
talkback.apk
talkback.odex
Upsell.apk
Upsell.odex
Velvet.apk
Velvet.odex
Videos.apk
Videos.odex
VoiceDialer_JB.apk
VoiceDialer_JB.odex
VoiceSearchStub.apk
VoiceSearchStub.odex
VuTalkbin.apk
VuTalkbin.odex
WeatherMultiCPbin.apk
WeatherMultiCPbin.odex
WeatherThemebin.apk
WeatherThemebin.odex
WifiCall.apk
WifiCall.odex
WiseScreen.apk
WiseScreen.odex

----

### 广告时间

本人人在美国，想卖苦力搞代购，挣点儿是点儿。各位看官如果有代购需求，可以通过QQ群 392496819，微信号：huaxiangco 和我联系。谢谢。

----

### 引用和版权

* 本文所有其他引用来源皆以超链接形式在文中给出。
* 本文欢迎转载，但请保留作者署名，广告信息和超链接。


# crawlers for entertainment

>一个致力于收集包括音乐榜单、游戏资讯、赛事资讯、电影榜单、美剧榜单等信息的娱乐向爬虫包

目前在学习python，于是练手之余写了这个demo，目前是初代，代码和功能都比较粗糙。

## 使用方法

```
python spider.py -s "name" -t "time" 
```


**name:** 选用的爬虫名称，目前包括 baidu_img、renren、douban、steam、163music、all（all是除了baidu_img的其他所有爬虫）

**time:** 爬虫的运行周期，单位是小时，默认24小时

所需模块：
~~urlib~~、re、os、~~impolib~~、~~sys~~、argparse、requests、json、time、pandas、beautifulsoup、~~apsheduler~~、schedule

所需环境：
python3.7

## 功能介绍

- 爬取steam热门游戏及特卖优惠游戏、网易云音乐四大榜单、豆瓣最近热门游戏、爬取人人影视热门美剧及美剧更新，以及根据关键词下载百度图片
- 定时爬取功能
- 将各类资讯分门别类存入csv文件，并以时间和类别命名

目标网络链接：

[https://image.baidu.com](https://image.baidu.com)

[https://movie.douban.com](https://movie.douban.com/explore#!type=movie&tag=%E7%83%AD%E9%97%A8&sort=recommend&page_limit=20&page_start=0)

[http://www.zmz2019.com](http://www.zmz2019.com)

[https://store.steampowered.com(热卖)](https://store.steampowered.com/search/?filter=globaltopsellers&page=1)

[https://store.steampowered.com(优惠)](https://store.steampowered.com/search/?os=win&specials=1&page=1)

[https://music.163.com/#/discover/toplist](https://music.163.com/#/discover/toplist)

[https://www.bilibili.com/ranking/all/0/0/1](https://www.bilibili.com/ranking/all/0/0/1)

To do:

- ~~完成音乐榜单爬取~~
- 完成体育资讯爬取
- ~~统一各爬虫风格~~
- ~~重构定时功能（放弃apsheduler，自己写一个），采用线程分配~~
- 打包成exe程序，或者写个小网页显示
- ~~异常时采用代理IP或者cookies（豆瓣会阻止异常IP访问）~~
- ~~采用类的调用，不使用os.system调用各爬虫~~
- ~~多User-Agent~~

---
新增功能：
- 增加哔哩哔哩单日热榜：python spider.py -s bilibili
- 增加资讯CSV文件邮件发送功能：python spider.py -m Y
sendEmail(from_addr,to_addr,password/authorization,host,title,content,annex)


P.S:后续问题：
- 没有自己写一个定时功能，因为发现时间好像不太准，所以采用了轻量模块schedule
- 代码风格统一了，但还是有个异性，暂时没法重复调用同一方法
- 免费代理IP不稳定，自动获取cookies也有障碍，目前采用多User Agent伪装，随机延迟经测试长时间有效
- 网易云音乐请求链接有加密，目前只能给出榜单，无法给出每首歌曲的具体链接
- 具体关于邮件发送问题，详见博客：



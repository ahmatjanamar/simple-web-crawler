# simple-web-crawler
a simple web crawler used for scraping some information from douban.com and make data analysis

we can use this project to scrape some data from the website

抖音网络爬虫地址  ： https://github.com/Python3WebSpider/DouYin
微信公众号爬虫地址： https://github.com/bowenpay/wechat-spider

Scrape   实战案例  爬取豆瓣读书

需求 ： 爬取豆瓣读书，并提取后续连续连接加入带爬取队列
链接分析： 
第一页的网址： https://book.douban.com/tag/%E7%BC%96%E7%A8%8B?start=0&type=T
第一页网址：https://book.douban.com/tag/%E7%BC%96%E7%A8%8B?start=20&type=T

在已有python项目中构建爬虫

这是一个能给scrapy 框架引入分布式的组件
分布式由redis 提供，可以在不同节点上运行爬虫，共用同一个redis 实例
在redis中存储实例爬取待的urls 与items 
 
爬取 scrapy follow true 试一试效果
代理： 在爬取过程中，豆瓣使用了反爬虫策略，可能会出现以下现象
则会相当于封了ip，， 所以，可以再爬取时使用代理来解决
思路： 在发起http请求之前，会经过下载中间件，自定义一个下载中间件，在其中临时获取一个代理地址，然后再发起HTTP请求
从xicidaili.com 中获取代理上找到免费代理，测试通过后，可以加入到代码中
1.  下载中间件，仿照middlewares。py中的下载中间件写，编写process reqest , 返回None 
豌豆IP 网站上获取ip代理

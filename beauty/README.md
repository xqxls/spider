# spider

> spider for beauty.

用于爬取妹子图片 的python爬虫程序

## 主要接口

> 定位到妹子图片资源

1. 获取指定url的html页面，进行译码和编码，然后通过bs转化为lxml形式，对其进行解析，选取所有图片信息的公共样式，放到select函数里，比如示例链接的公共样式为“li a img”
2. 经过select后，得到的是一个list，里面存放着img标签下的所有信息，我们可以取其中的图片链接和图片命名信息，图片链接可用于后面下载到本地

> 下载图片

1. 得到图片链接之后，便可以根据这个链接和主网站的链接获取图片实际的url，一般为主网站url+图片链接，不同网站会有差异
2. 确定url之后，就可以根据url，得到实际的图片资源，然后将图片资源存放到本地

## 注意事项

1. 请求url资源之前需要获取headers，模拟浏览器访问，可以任意打开一个网页，F12进入开发者模式，随便点开一个请求，即可找到‘User-Agent’
2. 部分网站爬取会存在中文乱码问题，甚至图片资源打不开，需要先译码，再编码为utf-8
3. 一般网站的分页，其url只是某个数字不同，所以可以利用循环获取所有页的url


## 导入模块

```
requests
bs4
```

## 参考资料

- [python 爬取猫眼电影top100数据](https://www.cnblogs.com/yocichen/p/11812637.html)

By xqxls 2021/3/22
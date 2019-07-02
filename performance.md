知识匮乏暴露了我的无知，从业这么久今天看react源码是遇到performance,一路追踪并没有发现performance的定义之处，连续找了两边，最后灵光一现，难道是浏览器的Api，搜了一下果然不出所料，而且这个Api很有用

### performance的作用

用于精确度量、控制、增强浏览器的性能表现，这个Api为测量网站性能，提供了以前没有办法做到的精度，可以精确到微妙级别

### Api介绍

1. navigationStart: 当前浏览器窗口的前一个网页关闭，发生unload事件时unix毫秒时间戳。如果没有前一个网页，等于fetchStart属性
2. unloadEventStart: 如果前一个网页与当前网页属于同一个域名，则返回前一个网页的unload事件法身的unix毫秒时间戳。如果没有前一个网页，或者之前一个网页与当前页面域名不同，则返回0
3. unloadEventEnd
4. loadEventStart
5. loadEvetEnd
6. fetchStart: 返回浏览器准备使用HTTP请求读取文档时的Unix毫秒时间戳。该事件在网页查询本地缓存之前发生
7. requestStart: 返回浏览器从服务器发出HTTP请求时的Unix毫秒时间戳
8. requestEnd
9. domLoading: 返回当前网页DOM结构开始解析时(即Document.readyState属性变为loading、相应的readystatechange事件触发时的unix毫秒时间戳)
10. domInteractive: 返回当前网页DOM结构结束解析、开始加载内嵌资源时（即Document.readyState属性变为“interactive"、相应的readystatechange事件触发时）的Unix毫秒时间戳
11. domContentLoadedEventStart：返回当前网页DomContentLoaded事件发生时（即DOM结构解析完毕、所有脚本开始运行时）的Unix时间戳
12. DomContentLoadedEventEnd：返回当前网页所有需要执行的脚本执行完时的Unix的时间戳

###### 方法

now: 返回当前网页从performance.timing.navagationStart 当当前事件之间的微妙

mask: 用于为相应的视点做标记

getEntries: 以数组的形式返回请求的时间统计信息


title: cross_domain
date: 2016-02-29 09:36:33
tags: javascript
---
<h3>iframe跨域</h3>
优点: 可以实现绝大部分跨域需求
缺点: 操作复杂
<h3>JSONP跨域</h3>
优点: 不受浏览器同源策略影响, 不需浏览器支持XMLhttpRequest
缺点: 仅支持get请求
<h3>CORS/HTTP5 XMLhttpRequest level 2</h3>
优点: 操作方便, 安全
缺点: 需要浏览器支持HTML5

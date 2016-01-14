title: express.js express-session
date: 2016-01-14 14:40:07
tags: node.js
---
express.js

  一般session是基于cookie来实现的，所以如果cookie被禁用，session会失效。
```javascript
  var session = require('express-session');
  var cookieParser = require('cookie-parser'); //express-session基于cookie
  app.use(cookieParser());
  app.use(session({
      secret: '12345',
      name: 'testapp',   //这里的name值得是cookie的name，默认cookie的name是：connect.sid
      cookie: {maxAge: 80000 },  //设置maxAge是80000ms，即80s后session和相应的cookie失效过期，如果不设置则，浏览器关闭失效
      resave: false,
      saveUninitialized: true,
  }));
```
一旦我们将express-session中间件用use挂载后，我们可以很方便的通过req参数来存储和访问session对象的数据。req.session是一个JSON格式的JavaScript对象，我们可以在使用的过程中随意的增加成员，这些成员会自动的被保存到option参数指定的地方，默认即为内存中去。

session与发送到客户端浏览器的生命周期是一致的。而我们在挂载session的时候，通过option选项的cookie.maxAge成员，我们可以设置session的过期时间，以ms为单位（但是，如果session存储在mongodb中的话，任何低于60s(60000ms)的设置是没有用的，下文会有详细的解释）。如果maxAge不设置，默认为null，这样的expire的时间就是浏览器的关闭时间，即每次关闭浏览器的时候，session都会失效。

有时候，我们需要session的声明周期要长一点，比如好多网站有个免密码两周内自动登录的功能。基于这个需求，session必须寻找内存之外的存储载体，数据库能提供完美的解决方案。这里，我选用的是mongodb数据库，作为一个NoSQL数据库，它的基础数据对象时database-collection-document 对象模型非常直观并易于理解，针对node.js 也提供了丰富的驱动和API。express框架提供了针对mongodb的中间件：connect-mongo，我们只需在挂载session的时候在options中传入mongodb的参数即可，程序运行的时候, express app 会自动的替我们管理session的存储，更新和删除
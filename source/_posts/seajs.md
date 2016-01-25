title: seajs
date: 2016-01-11 11:26:10
tags: 前端
---
```javascript
//exports 暴露引入

//require 引入依赖

//模块内的引入依赖和暴露接口
define(function (require, exports) {
  var util = require('./util.js');
  exports.init = function () {
    // Todo:
  }
});

//页面引入模块
seajs.use('dialog', function (Dialog) {
  // Todo: Dialog.init();
});

//异步加载js
define(function (require, exports) {
  if(false) {
    var util = require('./util.js'); //同步加载js,虽然用不到但是还是会加载js
  }
  setTimeout(function () {
    var util = require('./util1.js') //不会延迟5s加载js
  }, 5000);
  setTimeout(function () {
    var util = require.async('./util2.js'); //延迟5s加载js
  }, 5000);
});
```
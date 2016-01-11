title: seajs
date: 2016-01-11 11:26:10
tags: 前端
---

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
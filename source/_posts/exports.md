title: exports
date: 2016-02-15 14:31:27
tags: node.js
---
<h3>javascript模块化开发中exports和module.exports的区别</h3>
exports是module.exports的引用, 但是require最终返回的是module.exports

举个例子

```javascript
var module = {};
module.exports = {};
var exports = module.exports;

exports.a = 1;

// 此时module.exports.a = 1;

exports = "module.exports = {a:1}";

// 此时exports不再是module.exports的引用
// 给exports添加属性不再赋予module.exports
// 即此时exports不再是module.exports的引用
```
title: atom配置
date: 2016-03-22 14:47:21
tags: atom
---
如下代码添加到settings->Open Config Folder->styles.less
```less
// style the background and foreground colors on the atom-text-editor-element
// itself
atom-text-editor {
  font-family:Droid Sans Mono, Droid Sans Fallback;
}
// To style other content in the text editor's shadow DOM, use the ::shadow
// expression
atom-text-editor::shadow .cursor {
}
html, body, .tree-view, .tab-bar .tab,.bottom{
  font-family:Droid Sans Mono, Droid Sans Fallback;
}
.terminal {
  font-size:12px;
  font-family: Droid Sans Mono, Droid Sans Fallback;
}
.markdown-preview {
  h1,h2,h3,h4,h5,h6 {
    font-family: Droid Sans Mono, Droid Sans Fallback;
  }
}
```
Atom 终端快捷键ctrl + shift + P
安装包 apm install packageName
常用包名
activate-power-mode: 装逼酷炫神奇不解释
atom-beautify：这是个美化代码的插件，几乎支持所有主流的语言，完全可以满足前端同学的使用.
autocomplete-paths：常用IDE的同学会常常在引入图片的时候发现只要输入 . 或者/ 或者文件夹名称的时候就会自动显示出文件夹中的内容，非常的实用，强烈推荐.
autoprefixer：很多前端的同学在写css样式的时候常常忘记了添加兼容性前缀，例如-webkit-等内容.
color-picker: 作为一个有审美的设计向前端，常常需要确认自己的颜色属性是否是完美的，那么就需要这个插件，你就可以在任何一种颜色属性上看到一个完整的取色器.
docblockr：我们不仅仅要写代码，还要养成写好注释的习惯，而经常看开源框架的同学会发现那些大神的代码前都会有一段完美的注释，写清了所有的参数和使用方式，你会觉得大神不仅仅代码专业，态度也是非常的认真，其实，有了这个插件，你仅仅需要一个tab键就可以写出一样专业的注释！强烈推荐！！！
git-plus：虽然原生的Atom就支持了git命令，但是这个插件会让你更加喜欢在Atom中使用git，这非常方便在Windows上使用git的同学.
linter：你觉得你的代码写的很不专业吗？这个插件会自动提示你代码中不规范的地方，如果你希望得到更完整的提示的话可以尝试更加详细的系列，例如linter-jshint
markdown-format，markdown-writer：如果你不是Mac用户，并且十分喜欢使用markdown来写东西的话，那么你一定会爱上在Atom上写markdown的感觉~~
minimap：用过sublime text的同学一定知道右边那方便的缩略图，难道这么好用的工具Atom上会没有吗？不会！这个插件就会让你见到熟悉的缩略图，那么为什么要用插件呢？因为这个插件可以继续安装插件！你会发现一个真正强大的缩！略！图！
minimap-linter: 这个插件让你的缩略图显示的更加漂亮和完整
expose：当你一次性打开多个文件的时候也许你会使用分屏来查看，但是我相信你的屏幕不会大到让你无限的分屏，那么就需要在多个文件中切换，或者是查看多个文件，那么你可以点击最上边的标签，那有没有更方便的呢？有的！！那就是这个插件，shift+atl+e，就是这个效果：
<img src="http://images2015.cnblogs.com/blog/665852/201509/665852-20150926154753287-1557162353.png" />
就问你！美！不！美！

虽然原生的Atom就很漂亮了，但是既然Atom那么注重插件，主题用插件也是很常见的，在这里我就推荐我一直使用和十分推荐的一个主题，atom-material-ui，为什么我还要用这个插件呢？因为这个插件不仅仅配色很好看，更重要的是它有很多的动画，让你的编辑器更加生动，你会更喜欢它的，每天打码的心情都会好很多哦~但是有个注意的地方，如果你使用了酷炫的expose插件的话，需要在主题的插件中将
<img src="http://images2015.cnblogs.com/blog/665852/201509/665852-20150926155024069-505114015.png" />
这里关闭，否则expose插件不会出现那么酷炫的效果。

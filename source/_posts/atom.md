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

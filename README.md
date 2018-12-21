# 适用于Froala Editor的代码编辑器插件
---
## 此插件适用于Froala Editor,且Froala Editor使用的div标签作为容器
#### 如果是textare标签作为容器,请勿使用,有严重问题:丢失html标签和内容
---
示例代码在src下,[src/codeInsert.html](src/codeInsert.html)为编辑器使用示例,[src/showInsertCode.html](src/showInsertCode.html)为在其他页面高亮代码使用示例
主要文件:
* [src/css/code.css](src/css/code.css)
* [src/js/code.js](src/js/code.js)
* [src/js/ext-static_highlight.js](src/js/ext-static_highlight.js)
不要使用ace editor下面的ext-static_highlight.js,除非你把src/js/ext-static_highlight.js拷贝过去替换了它.否则请用src/js/ext-static_highlight.js这个文件
---
使用之前的准备:
修改ace editor的主文件ace.js(本项目中这个js已经被修改了):
将
```javascript
if (cjk) {
    screenColumn += 1;
    var span = dom.createElement("span");
    span.style.width = (self.config.characterWidth * 2) + "px";
    span.className = "ace_cjk";
    span.textContent = cjk;
    valueFragment.appendChild(span);
}
```
修改为
```javascript
if (cjk) {
    screenColumn += 1;
    var span = this.dom.createElement("span");
    span.style.width = (self.config.characterWidth * 2) + "px";
    span.className = "ace_cjk";
    span.textContent = cjk;
    valueFragment.appendChild(span);
}
```
之后参考两个示例文件.
---
注意:
请将src/js下的ext-static_highlight.js放到ace editor目录下替换对应文件再引用该文件.示例中直接引用的src/js下的文件,你也可以这样引用
---
main files:
* [src/css/code.css](src/css/code.css)
* [src/js/code.js](src/js/code.js)
* [src/js/ext-static_highlight.js](src/js/ext-static_highlight.js)
do not reference ace editor's ext-static_highlight.js file.use src/js/ext-static_highlight.js instead.
---
if you need to input CJK char(like chinese,japanese...),please modify ace.js.
change
```javascript
if (cjk) {
    screenColumn += 1;
    var span = dom.createElement("span");
    span.style.width = (self.config.characterWidth * 2) + "px";
    span.className = "ace_cjk";
    span.textContent = cjk;
    valueFragment.appendChild(span);
}
```
to
```javascript
if (cjk) {
    screenColumn += 1;
    var span = this.dom.createElement("span");
    span.style.width = (self.config.characterWidth * 2) + "px";
    span.className = "ace_cjk";
    span.textContent = cjk;
    valueFragment.appendChild(span);
}
```
after that, please flow [src/codeInsert.html](src/codeInsert.html) and [src/showInsertCode.html](src/showInsertCode.html)
DO NOT USE IT IF YOU USE textarea FOR Froala Editor.IT ONLY FOR div TAG.

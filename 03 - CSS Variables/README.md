# CSS Variables


[效果，请点链接](https://qinjingfei.github.io/JS30/03%20-%20CSS%20Variables/index-jing.html)


## 要点

* `:root`
* `var(--xx)` CSS 变量
* `filter:blur()`
* 事件`change`, `mousemove`


## 知识点

* NodeList 与 Array的区别

NodeList 并不能使用 Array的方法
```
const inputs = document.querySelectorAll('.controls input'); //NodeList

```

如何将NodeList转化为Array

通过Array.prototye.slice 可以将NodeList 转化为数组，并可以用数组的方法了.

```
var slice = Array.prototype.slice;
var dom = slice.call(document.querySelectorAll(selector))

```
[想要了解更多的NodeList, 点这里](http://devdocs.io/dom/nodelist)

* HTML5 的自定义属性`dataset`

Example

```
<div id="user" data-id="1234567890" data-user="johndoe" data-date-of-birth>John Doe</div>

const el = document.querySelector('#user');

// el.id == 'user'
// el.dataset.id === '1234567890'
// el.dataset.user === 'johndoe'
// el.dataset.dateOfBirth === ''
```
[dataset](https://github.com/soyaine/JavaScript30/tree/master/03%20-%20CSS%20Variables)

[想要了解更多的dataset, 点这里](http://devdocs.io/dom/htmlelement/dataset)

* CSS Variables

CSS 自定义属性，可以被重复使用。 用法 `--*`


* `:root` 
 
`:root`匹配文档的根元素，也就是`<hmtl>`标签

Example

```
//全局CSS变量
:root {
  --color: #fff;
}

img {
  background: var(--base);
}

```
[:root](http://devdocs.io/css/:root)


* CSS滤镜 filter

[filter](http://devdocs.io/css/filter)

* CSSStyleDeclaration.setProperty(如何用JS改变CSS属性值)

`document.documentElement`代表文档根元素

```
document.documentElement.style.setProperty('--base', '#fff');
```

* 如何处理参数值(一个有px, 另一个没有)

```
const suffix = this.dataset.sizing || ''; 
```

## 有用的链接

[soyaine的笔记](https://github.com/soyaine/JavaScript30/tree/master/03%20-%20CSS%20Variables)
# JS和CSS钟表


## 要点

* 指针：旋转的效果
* 获取实时时间

### 涉及的点:

* `transform-origin`
* `transform: rotate()`
* `transition`
* transition-timing-function: cubic-bezier(x,x,x,x)
* setInterval(callback, time)
* new Date()

## 知识点

* 设置指针的初始位置（旋转的轴点）
	* `transform-origin`
* 指针跳动时的过渡效果
	* `transition-time-function`
* 访问元素的样式
任何支持 style 特性的 HTML 元素在 JavaScript 中都有一个对应的 style 属性(property)。

[这里是一些介绍](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)

[这里是CSS Properties Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Properties_Reference)

* 这里想到一个问题JS 中property 和 attribute 的区别?

[其它请看soyaine 总结的很仔细](https://github.com/soyaine/JavaScript30/tree/master/02%20-%20JS%20%2B%20CSS%20Clock)



## Bug

```
const secondDeg = (second / 60)  * 360 + 90;
```
second = 60 时, secondDeg = 450 下一秒

second = 0 时, secondDeg = 90 这会造成指针从450度闪到90度

### 解决方法

在90度时，取消`transition`属性

```
secondHand.style.transition = (secondDeg === 90)?'all 0s':'all .5s'
```

[soyaine的解决方法](https://github.com/soyaine/JavaScript30/tree/master/02%20-%20JS%20%2B%20CSS%20Clock)
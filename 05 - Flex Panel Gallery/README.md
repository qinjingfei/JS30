# Flex Panel Gallery

[效果](https://qinjingfei.github.io/JS30/05%20-%20Flex%20Panel%20Gallery/index-jing.html)

[soyaine的笔记](https://github.com/soyaine/JavaScript30/tree/master/05%20-%20Flex%20Panel%20Gallery)

## 知识点

* flex

[A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

* transform: translateX/translateY
```
 .panel > *:first-child{
    	transform: translateY(-100%);
    }

    .panel.open-active > *:first-child{
    	transform: translateY(0);
    }

    .panel > *:last-child{
    	transform: translateY(100%);
    }

    .panel.open-active > *:last-child{
    	transform: translateY(0);
    }

```

* css selector `.class.class`

`.class.class` matches any elements with both classes
`.class .class` matches  any elements of class `.class` that are descendants of another element with the class `.class` 


* element.classList.toggle()

```
function toggleOpen(){
	this.classList.toggle('open')
}
panels.forEach(panel => panel.addEventListener('click', toggleOpen));
```
* transitionend事件

```
function toggleActive(e){
if(e.propertyName.includes('flex')){
	this.classList.toggle('open-active');
}
}
panels.forEach(panel => panel.addEventListener('transitionend', toggleActive));
```



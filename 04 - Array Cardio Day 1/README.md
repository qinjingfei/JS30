# Array Cardio 指南

[soyaine的笔记](https://github.com/soyaine/JavaScript30/tree/master/04%20-%20Array%20Cardio%20Day%201)

## 效果

简单的介绍一些Array.prototype的方法， 比如 Array.prototype.filter, Array.prototype.map, Array.prototype.reduce等（这些都被常用于higher order function）
在我以前学的CMPS112 Comparative Languages 里很像，都是functional language. 因为，我比较熟悉这些方法，我就列举一些例子.

[CMPS112笔记](https://www2.ucsc.edu/courses/cmps112-wm/:/Lecture-notes/)

## 要点

* filter
* reduce
* map
* sort
* ES6 array matching


## 知识点

* filter

Example: 去重(去除array中相同的元素)

```
var uniq = function (array){
    return array.filter((item, index) => array.indexOf(item) == index)
}

```

备注：The `indexOf()` method returns the first index at which a given element can be found in the array, or -1 if it is not present.

[indexOf链接](http://devdocs.io/javascript/global_objects/array/indexof)
[filter链接](http://devdocs.io/javascript/global_objects/array/filter)

* reduce

Example: 

```
const totalYears = inventors.reduce((total, inventor) => {
      return total + (inventor.passed - inventor.year);
    }, 0);
```

[Fun Fun Function Reduce](https://www.youtube.com/watch?v=Wl98eZpkp-c)

* map

```
 const fullNames = inventors.map(inventor => `${inventor.first} ${inventor.last}`);
```


[Fun Fun Function Map](https://www.youtube.com/watch?v=bCqtb-Z5YGQ)


* sort && ES6 destructuring

Example:

```
const alpha = people.sort((lastOne, nextOne) => {
      const [aLast, aFirst] = lastOne.split(', ');
      const [bLast, bFirst] = nextOne.split(', ');
      return aLast > bLast ? 1 : -1;
    });
```

假如 `const people = "['Beck, Glenn', 'Becker, Carl']"`, 在这种情况下，
```
lastOne = 'Beck, Glenn'
nextOne = 'Becker, Carl'
aLast = 'Beck'
aFirst = 'Glenn'
bLast = 'Becker'
bFirst = 'Carl'

```

为什么我们要使用destructuring?

Example:

```
makeSound({weight: 23, sound:'woof'})

// without destructuring

function makeSound(options){
	var species = options.species || 'animal'
	var sound = options.sound
	console.log('The' + species + ' says' + sound + '!')
}

//with destructuring

functiong makeSound({species="animal", sound}){
	console.log('The' + species + ' says' + sound + '!')
}

```
`destructuring 可以使代码更简洁，易读`


[ES 6 array matching](http://es6-features.org/#ArrayMatching)

[Destucturing]（https://www.youtube.com/watch?v=PB_d3uBkQPs&t=330s）
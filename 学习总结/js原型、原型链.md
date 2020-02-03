## js原型、原型链

所有的 JavaScript 对象都会从一个 prototype（原型对象）中继承属性和方法。

只要你创建一个函数，它就自带prototype属性

一张图看懂原型、原型链之间的关系![QQ截图20200201175801](js原型、原型链/QQ截图20200201175801.png)

```javascript
function Person() {

}
// 虽然写在注释里，但是你要注意：
// prototype是函数才会有的属性
Person.prototype.name = 'Kevin';
var person1 = new Person();
var person2 = new Person();
console.log(person1.name) // Kevin
console.log(person2.name) // Kevin


function Person() {

}

Person.prototype.name = 'Kevin';

var person = new Person();

person.name = 'Daisy';
console.log(person.name) // Daisy

delete person.name;
console.log(person.name) // Kevin
```


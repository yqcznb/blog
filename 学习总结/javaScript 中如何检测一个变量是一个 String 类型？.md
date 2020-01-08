##  **javaScript 中如何检测一个变量是一个 String 类型？** 

 **答案：三种方法（typeof、constructor、Object.prototype.toString.call()）** 

1. 你可以使用 typeof 操作符来检测变量的数据类型。 

+ typeof运算符的返回类型为字符串，值包括如下几种：
  +  'undefined'       --未定义的变量或值
  + 'boolean'         --布尔类型的变量或值

  + 'string'           --字符串类型的变量或值
  + 'number'         --数字类型的变量或值
  + 'object'          --对象类型的变量或值，或者null(这个是js历史遗留问题，将null作为object类型处理)
  + 'function'         --函数类型的变量或值

  typeof是一个运算符，有2种使用方式：typeof(表达式)和typeof 变量名，第一种是对表达式做运算，第二种是对变量做运算。 

```javascript
typeof('123') === "string" // true

typeof '123' === "string" // true
```

2. constructor 属性返回对创建此对象的数组函数的引用。 

   ```javascript
   <script type="text/javascript">
   
   var test=new Array();
   
   if (test.constructor==Array)
   {
   document.write("This is an Array");
   }
   if (test.constructor==Boolean)
   {
   document.write("This is a Boolean");
   }
   if (test.constructor==Date)
   {
   document.write("This is a Date");
   }
   if (test.constructor==String)
   {
   document.write("This is a String");
   }
   
   </script>
   ```

   ```javascript
   '123'.constructor === String // true
   ```

3.Object.prototype.toString.call()

```javascript
Object.prototype.toString.call('123') === '[object String]' // true
```

 在`JavaScript`里使用`typeof`判断数据类型，只能区分**基本类型**，即：`number`、`string`、`undefined`、`boolean`、`object`。
对于`null`、`array`、`function`、`object`来说，使用`typeof`都会统一返回`object`字符串。
要想区分对象、数组、函数、单纯使用`typeof`是不行的。在JS中，可以通过`Object.prototype.toString`方法，判断某个对象之属于哪种内置类型。
分为`null`、`string`、`boolean`、`number`、`undefined`、`array`、`function`、`object`、`date`、`math`。

```javascript
`Object.prototype.toString.call(``null``); ``// "[object Null]"``Object.prototype.toString.call(undefined); ``// "[object Undefined]"``Object.prototype.toString.call(“abc”);``// "[object String]"``Object.prototype.toString.call(123);``// "[object Number]"``Object.prototype.toString.call(``true``);``// "[object Boolean]"`
```
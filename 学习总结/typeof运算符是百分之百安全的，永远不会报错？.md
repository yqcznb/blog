# typeof运算符是百分之百安全的，永远不会报错？

**在没有let之前，typeof运算符是百分之百安全的，永远不会报错。**

**现在这一点不成立了。这样的设计是为了让大家养成良好的编程习惯，变量一定要在声明之后使用，否则就报错。**

+ 如果一个变量根本没有被声明，使用typeof反而不会报错

  ```javascript
  typeof undeclared_variable // "undefined"
  ```

+ 只要块级作用域内存在let命令，它所声明的变量就“绑定”（binding）这个区域，不再受外部的影响。

  ```javascript
  var tmp = 123;
  
  if (true) {
    tmp = 'abc'; // ReferenceError
    let tmp;
  }
  ```

+ 这时候他就会报错了。
+ ES6 明确规定，如果区块中存在let和const命令，这个区块对这些命令声明的变量，从一开始就形成了封闭作用域。凡是在声明之前就使用这些变量，就会报错。
+ 总之，在代码块内，使用let命令声明变量之前，该变量都是不可用的。这在语法上，称为“暂时性死区”
+ “暂时性死区”也意味着typeof不再是一个百分之百安全的操作，因此，typeof运行时就会抛出一个ReferenceError错误。

**在调试JavaScript程序的时候经常遇到两个错误：ReferenceError和TypeError。**
**1.首先：字面上的意思分别为引用错误和类型错误；** 
**2.作用域：ReferenceError就是在作用域中找不到、TypeError是在作用域中找到了但是 做了它不可能做的事情。**
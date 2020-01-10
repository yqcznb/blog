##  **require 与 import 的区别** 

**第一、两者的加载方式不同**

+ require 是在运行时加载，所以require理论上可以运用在代码的任何地方 。

+ 而 import 是在编译时加载，所以必须放在文件开头 。

require('./a')(); // a 模块是一个函数，立即执行 a 模块函数

var data = require('./a').data; // a 模块导出的是一个对象

var a = require('./a')[0]; // a 模块导出的是一个数组 ======> 哪都行

import $ from 'jquery';

import * as _ from '_';

import {a,b,c} from './a';

import {default as alias, a as a_a, b, c} from './a'; ======>用在开头

**第二、规范不同**

+ require 是 CommonJS/AMD 规范

+ import 是 ESMAScript6+规范

+ import是es6的一个语法标准，如果要兼容浏览器的话必须转化成es5的语法 

**第三、require 特点：**社区方案，提供了服务器/浏览器的模块加载方案。非语言层面的标准。只能在运行时确定模块的依赖关系及输入/输出的变量，无法进行静态优化。

import 特点：语言规格层面支持模块功能。支持编译时静态分析，便于 JS 引入宏和类型检验。动态绑定。

**本质**

require是赋值过程，其实require的结果就是对象、数字、字符串、函数等，再把require的结果赋值给某个变量

import是解构过程，但是目前所有的引擎都还没有实现import，我们在node中使用babel支持ES6，也仅仅是将ES6转码为ES5再执行，import语法会被转码为require

require时代的模块

node编程中最重要的思想之一就是模块，而正是这个思想，让JavaScript的大规模工程成为可能。模块化编程在js界流行，也是基于此，随后在浏览器端，requirejs和seajs之类的工具包也出现了，可以说在对应规范下，require统治了ES6之前的所有模块化编程，即使现在，在ES6 module被完全实现之前，还是这样。

 详细用法可以查看：

 https://www.cnblogs.com/ranyonsue/p/10861276.html 

 https://www.cnblogs.com/myfirstboke/p/10563597.html 
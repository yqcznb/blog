## 解决本地引用less跨域问题

Less 是一门 CSS 预处理语言，它扩展了 CSS 语言，增加了变量、Mixin、函数等特性，使 CSS 更易维护和扩展。

Less 可以运行在 Node 或浏览器端。

在 Node.js 环境中使用 Less ：

```
npm install -g less
```

对于less在node环境中怎么使用less中文网上已经很明确了，可以自行学习。

下面主要说一下less怎么在浏览器端使用。

+ ##### 在浏览器端

  1.去 [中文网](http://lesscss.cn/#download-options)下载最新的less,或者引入有效的CDN也可以，但是这样会有跨域问题。在本地是不行的。

  2.所以就需要在本地配到服务器端，这样就可以避免跨域问题。

  + 在本地IIS里面新建一个网站，首页就是index.html文件
  + 然后指定一个端口号，在本地localhost：端口号访问就行了。

+ 还有一个方法更简单。就是直接把less写到html里面

  、、、html

  <!DOCTYPE html>
  <html>
  	<head>
  		<meta charset="UTF-8">
  		<title></title>	
  	<style type="text/less">
          .ccc{
              height: 60px;
              background-color: #ccc;
              .left{
                  color: green;
              }
              .right{
                  color: red;
              }
          }
      </style>
  <script src="less.js"></script>
  	</head>
  	<body>
  		<div class="ccc">1111111111</div>
  		111
  	</body>
  </html>
、、、

+ 你要告诉它里面的是less就可以运行了，就是这么简单。

  


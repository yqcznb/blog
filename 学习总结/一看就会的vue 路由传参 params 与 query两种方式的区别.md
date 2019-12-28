# 一看就会的vue 路由传参 params 与 query两种方式的区别

***这么说容易理解：query相当于get请求，页面跳转的时候，可以在地址栏看到？+传的值，而params相当于post请求，参数不会再地址栏中显示。***

```javascript
//query传参 这里路径用的是path
this.$router.push({
        path:'/xxx'
        query:{
          id:id
        }
      })
  
//query接收参数:
this.$route.query.id

//params传参 这里路径用的是name
this.$router.push({
        name:'xxx'
        params:{
          id:id
        }
      })
  
接收参数:
this.$route.params.id
```

### **`传参是this.$router,接收参数是this.$route,`**
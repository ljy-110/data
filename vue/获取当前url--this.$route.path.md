用vue router如何获得当前页面的路由url-->this.$route.path

```js
this.$route.path
```

获取当前地址栏的url

```js
window.location.href
```

vue监听路由变化

```vue
watch:{
  $route(to,from){
    console.log(to.path);
  }
},

或者

watch: {
  $route: {
    handler: function(val, oldVal){
      console.log(val);
    },
    // 深度观察监听
    deep: true
  }
},

或者

// 监听,当路由发生变化的时候执行
watch: {
  '$route':'getPath'
},
methods: {
  getPath(){
    console.log(this.$route.path);
  }
}
```


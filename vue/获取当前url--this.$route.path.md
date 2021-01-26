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

```
beforeRouteLeave(to, from, next) {
    next()
},
beforeRouteEnter(to, from, next) {
    next()
},
beforeRouteUpdate(to, from, next) { // 用于相同路由组件的的参数更新
    next()
},
data:{},
method: {}

//
beforeRouteLeave(to, from, next) {
    console.log(this.ruleForm || this.src);
    if(this.ruleForm || this.src){
      this.$confirm('是否将你填写的数据保存为草稿？')
      .then(_ => {
        // next()
      })
      .catch(_ => {
        next()
      });
    }else{
      next()
    }
  },
```


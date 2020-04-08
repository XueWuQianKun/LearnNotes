### 指令 

|                  |              |              |            |               |              |
| :--------------: | :----------: | :----------: | :--------: | :-----------: | :----------: |
| [{{ 插值 }}](#0) | [v-html](#1) | [v-bind](#2) | [v-if](#3) | [v-model](#4) | [过滤器](#5) |
|    [v-on](#6)    |              |              |            |               |              |



​	<h3 id='0'>`{{ message }}`</h3>

> 常用的插值表达式

``` vue
{{ message }}

<script>
data(){
  return{
    message:"message"
  }
}
</script>
```

​	<h3 id='1' style="color:red"> `v-html`</h1>

> 用于绑定html属性

```vue
<div v-html="html"></div>
<script>
data(){
  return{
    html:'<h2>html片段</h2>'
  }
}
</script>
```

​	<h3 id='2'>`v-bind`</h3>

> 被用来响应地更新 所绑定的html 属性  `v-bind=` 可简写为 `:`

``` vue
<div v-bind:class='class'>
</div>
<script>
	data:{
    class:'style中定义的class name'
  }
</script>
```

​	<h3 id ='3'>`v-if`</h3>

> v-if 指令将根据绑定 的值(true 或 false )来决定是否插入 p 元素

```vue
<p v-if='seen'></p>
<script>
data:{
  seen:true // or false
}
</script>
```

​	<h3 id='4'>`v-model`</h3>

>  v-model 指令来实现双向数据绑定

```vue
<input v-model="message">
<script>
data:{
  message:""
}
</script>
```

​	<h3 id='5'>`过滤器`</h3>

> 过滤器函数接受表达式的值作为第一个参数
>
> > 且： 	{{ message | filterA | filterB }}  可串联

```vue
<div id="app">
  {{ message | filter }}
</div>
<script>
  new Vue({
    el:'#app',
    data:{
      message:"webDeveloper"
    },
    filters:{
      filter(value){
        // ....处理value略
        retrun newValue
      }
    }
  })
</script>
```

​	<h3 id='6'>`v-on`</h3>

> 绑定事件的监听     `v-on=` 可简写为 `@`

~~~vue
<button v-on="buttonClick"></button>
<script>
new Vue({
  methods:{
    buttonClick(){
      alert("button被点击了")
    }
  }
})
</script>
~~~




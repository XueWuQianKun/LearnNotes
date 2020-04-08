### 条件语句

​	<h3 id='0'>`v-if`  &  `v-else` & `v-else-if`</h3>

> 条件语句

```vue
<div v-if="type === 'A'">A</div>
<div v-else-if="type === 'B'">B</div>
<div v-else="type === 'C'">C</div>
<script>
data:{
  type:'C'
}
</script>
```

​	<h3 id='1'>`v-show`</h3>

> 可以使用 v-show 指令来根据条件展示元素

```vue
<h1 v-show="ok">Hello!</h1>
```

### 循环语句

​	<h3 id='1'>`v-for`</h3>

> ​	*1.* 迭代数组 

```vue
<div id="app">
  <ol>
    <li v-for="obj in names">
    	{{ obj.name }}
    </li>
  </ol>
  <!--
也可以用在 template 中
<ul>
  <template v-for="obj in sites">
    <li>{{ obj.name }}</li>
    <li>--------------</li>
  </template>
</ul>
--> 
</div>
<script>
new Vue = ({
  el:"#app",
  data:{
    names:[
      {name:"张三"},
      {name:"李四"},
      {name:"王五"}
    ]
  }
})
</script>
```

> *2.* 迭代对象

```vue
<div id="app">
  <!--1 取value-->
  <ul>
    <li v-for="value in object">
    	{{ value }}
    </li>
  </ul>
  <!--2 取 value key-->
   <ul>
    <li v-for="(value,key) in object">
    	{{ key }} : {{ value }}
    </li>
  </ul>
  <!--3 取 value key index-->
   <ul>
    <li v-for="(value,key,index) in object">
    	 {{ index }}.{{ key }} : {{ value }}
    </li>
  </ul>
  <!--4 迭代整数-->
  <ul>
    <li v-for="i in 10">
    	{{ i }}
    </li>
  </ul>
</div>
<script>
new Vue({
  el:"#app",
  data:{
    object:{
      name:"my notes",
      message:"我的笔记",
 			age:25
    }
  }
})
</script>
```


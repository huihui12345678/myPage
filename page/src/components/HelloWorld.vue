<template>
  <div class="hello">
  	<div class="header">
  		<div></div>
  	</div>
  	<div class="main">
  			<div class="content1">
  				<label>用户名：<input type="text" v-model="user"/></label>
  				
  			</div>
  			<div class="content2">
  				<label>密码：&nbsp;<input type="password" v-model="password1" /></label>
  				
  			</div>
  		
  	</div>
  	<ul class="footer">
  			<router-link  :to="{ path: '/IndexPage' }" active-class="login" tag="li" > 
			<span >登录</span>
		</router-link>
  	</ul>    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      user:'zhangsan',
      password1:''
    }
  },
  created (){
 
  },
  watch: {
  	
  },
  beforeRouteLeave (to, from, next) {
  	if(!this.password1||!this.user){
  		next(false)
  	}else{
  		next()
  	}
    // 在当前路由改变，但是该组件被复用时调用
    // 举例来说，对于一个带有动态参数的路径 /foo/:id，在 /foo/1 和 /foo/2 之间跳转的时候，
    // 由于会渲染同样的 Foo 组件，因此组件实例会被复用。而这个钩子就会在这个情况下被调用。
    // 可以访问组件实例 `this`
  },
  methods: {
// login(){
//  		this.$axios.get('../static/data.json')
//.then(function (response) {
//  console.log(response);
//})
//.catch(function (error) {
//  console.log(error);
//});
// }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
	ul {
  list-style-type: none;
  padding: 0;
  
}
.hello{
	border: 1px solid gainsboro;
	border-radius: 5px;
	height: 210px;
	width: 300px;
	margin: auto;
	box-shadow: 2px 2px 2px 2px #f3f1f1;
}
.hello div{
	width: 100%;
}
.header{
	height: 30px;
	background: #f3f1f1;
}
.header div{
	width: 25px;
	height: 25px;
	
}
.content1{
	height: 60px;
	border-bottom:1px solid gainsboro;
}
.content2{
	height: 60px;
	border-bottom:1px solid gainsboro;
}
label{
	  margin: 18px 0;
    display: inline-block;
}
li{
	    position: relative;
    left: 40px;
    background: #f3f1f1;
    padding: 2px 0;
    width: 70px;
    border: 1px solid gainsboro;
    border-radius:2px;
    box-shadow: 2px 2px 2px 2px #f3f1f1;
}
</style>

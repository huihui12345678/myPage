<template>
  <div class="hello">
  	<div class="header">
  		<span></span>
  	<span>用户名：</span><span>{{user}}</span>
  		<span>所属部门：</span><span>{{department}}</span>
  	</div>
  	<div class="main">
  			<div class="content1">
  			
  				<h5>{{msg}}</h5>
  			</div>
  			<div class="content2">
  			
  				
  			</div>
  			
  			
  		
  	</div>
  	<ul class="footer">
  			<router-link  :to="{ path: '/' }" active-class="login" tag="li"> 
			退出
		</router-link>
  	</ul>    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: '欢迎光临考试系统...',
      user:'zhangsan',
      department:''
    }
  },
  created (){
    		this.$axios.get('../static/data.json')
  .then( (res)=> {
    console.log(res);
     
     this.user=res.data.usercode
     	this.department=res.data.comcode
    
//   this.$nextTick(function () {
//  
//     this.user=res.data.usercode
//   	this.department=res.data.comcode
//      // DOM 现在更新了
//      // `this` 绑定到当前实例
//      
//    })
  })
  .catch( (error)=> {
    console.log(error);
  });
  },
  mounted(){
 
  },
  methods:{
  
  },
	msg1(res){
   
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
h5{
	margin: 0;
}
.content1{
	height: 60px;
	/*border-bottom:1px solid gainsboro;*/
}
.content2{
	height: 60px;
	border-bottom:1px solid gainsboro;
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

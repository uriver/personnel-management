<template>
	<div class="umess-container">
		<div class="umess-lr"></div>
		<div class="umess-center">
			<div style="margin-top:50px"></div>
			<div class="weekly-line">
				<h1>个人信息</h1>
			</div>
			<div class="umess-left">
				<label><p>姓名：</p>{{ userMes.name }}</label>
				<br />				
				<label><p>性别：</p>{{ userMes.sex }}</label>
				<br>
				<label><p>工号：</p>{{ userMes.jobID }}</label>
				<br>					
				<label><p>学号：</p>{{ userMes.sid }}</label>	
				<br>				
				<label><p>年级：</p>{{ userMes.grade }}</label>	
				<br>				
				<label><p>专业：</p>{{ userMes.major }}</label>
				<br>				
				<label><p>邮箱：</p>{{ userMes.email }}</label>	
				<br>				
				<label><p>QQ：</p>{{ userMes.qq }}</label>	
				<br>				
				<label><p>手机号：</p>{{ userMes.tel }}</label>		
				<br>				
				<label><p>辅导员：</p>{{ userMes.instructor }}</label>
				<br>				
				<label><p>研究室：</p>{{ userMes.resOffice }}</label>	
				<br>				
				<label><p>是否退出：</p>{{ userMes.exit }}</label>	
				<br>				
				<label><p>出生日期：</p>{{ userMes.date }}</label>	
				<br>				
				<label><p>身份证号：</p>{{ userMes.id }}</label>		
			</div>
			<div class="umess-right">
				<label><p>实验室小组：</p>{{ userMes.group }}</label>	
				<br>				
				<label><p>所在办公室：</p>{{ userMes.office }}</label>	
				<br>								
				<label><p>加入中心时间：</p>{{ userMes.joinTime }}</label>
				<br>
				<label><p>紧急联系人：</p>{{ userMes.emergencyContact }}</label>
				<br />				
				<label><p>紧急联系电话：</p>{{ userMes.emergencyTelephone }}</label>
				<button class="umess-btn" @click="changeMessage">修改信息</button>
			</div>
		</div>
		<div class="umess-lr"></div>
	</div>
</template>

<script>
  export default {
    data () {
      return {
      	userMes:{},
        radio: '1'
      };
    },
    mounted:function(){
    	this.getData();
    },
    methods:{
    	getData:function(){
    		var self = this;
	        this.$http.get("/static/user-message.json").then(function(res){
	          console.log(res.data);
	          self.userMes = res.data;
	        })
    	},
    	changeMessage: function(){
    		this.$router.push({ path: '/userpage/user-cgmes' })
    	}
    }
  }
</script>

<style>
	.umess-container{
		width: 100%;
		height: 100%;
		display: flex;
	}
	.umess-lr{
		flex: 1.5;
	}
	.umess-center{
		flex: 4;
	}
	.umess-center h1{
		font-weight: 300;
	}
	.umess-line{
		width: 700px;
		height: 60px;
		margin-bottom: 24px;
		border-bottom: 1px solid #BABABA;
	}
	.umess-left{
		width: 42%;
		float: left;
	}
	.umess-left p{
		display: inline-block;
		width: 120px;
		height: 0;
		text-align: right;
	}
	.umess-right{
		width: 45%;
		margin-left: 20px;
		float: left;
	}
	.umess-right p{
		display: inline-block;
		width: 170px;
		height: 0;
		text-align: right;
	}
	.umess-btn{
		width: 160px;
		height: 35px;
		display: block;
		margin: 45px auto;
		background-color: #1D8CE0;
		border: none;
		color: white;
		font-size: 18px;
	}
	.umess-btn:hover{
		cursor: pointer;
		background-color: #20A0FF;
	}
	.umess-btn:active{
		color:rgba(250,128,114,0.7);;
	}
	.umess-btn:focus{
		outline:none;
	}
</style>
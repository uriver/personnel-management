<template>
	<div class="umess-container">
		<div class="umess-lr"></div>
		<div class="umess-center">
			<div style="margin-top:50px"></div>
			<div class="weekly-line">
				<h1>个人信息</h1>
			</div>
			<div class="umess-left">
				<label><p>姓名：</p>张三</label>
				<br />				
				<label><p>性别：</p>男</label>
				<br>				
				<label><p>学号：</p>1404XXX</label>	
				<br>				
				<label><p>年级：</p>大三</label>	
				<br>				
				<label><p>专业：</p>计算机科学与技术</label>
				<br>				
				<label><p>邮箱：</p>123456@qq.com</label>	
				<br>				
				<label><p>QQ：</p>123456</label>	
				<br>				
				<label><p>手机号：</p>1786270XXXX</label>		
				<br>				
				<label><p>辅导员：</p>赵权睿</label>
				<br>				
				<label><p>研究室：</p>329研究室</label>	
				<br>				
				<label><p>是否退出：</p>否</label>	
				<br>				
				<label><p>出生日期：</p>1995年1月1日</label>	
				<br>				
				<label><p>身份证号：</p>4302XX19950101XXXX</label>		
			</div>
			<div class="umess-right">
				<label><p>实验室小组：</p>云计算小组</label>	
				<br>				
				<label><p>所在办公室：</p>330办公室</label>	
				<br>								
				<label><p>加入中心时间：</p>一年</label>
				<br>
				<label><p>紧急联系人：</p>李四</label>
				<br />				
				<label><p>紧急联系电话：</p>1786270XXXX</label>
				<button class="umess-btn">修改信息</button>
			</div>
		</div>
		<div class="umess-lr"></div>
	</div>
</template>

<script>
  export default {
    data () {
      return {
        radio: '1'
      };
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
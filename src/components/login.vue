<template>
	<div id="login-container">
		<div class="login-font">
			<p>LOGIN</p>
		</div>
		<div class="login-center">
			<div class="login-user" v-show="show">
				<form>
					<div>
						账号：<input class="login-input" type="text" name="user"/>
					</div>
					<div class="psd-set"> 
						密码：<input class="login-input" type="text" name="psd"/>
					</div>
					<button class="btn-submit" @click="userLogin()">登 录</button>
				</form>
			</div>
			<div class="login-admin" v-show="!show">
				<form>
					<div>
						管理员账号：<input class="login-input" type="text" name="ad-user"/>
					</div>
					<div class="psd-set"> 
						管理员密码：<input class="login-input" type="text" name="ad-psd"/>
					</div>
					<button class="btn-submit" @click="adminLogin()">登 录</button>
				</form>
			</div>
			<div class="login-choose el-icon-setting" @click="changeShow()"> 切换至{{identity}}登录</div>
		</div>
	</div>
</template>

<script>
	export default{
		data(){
			return {
				show:true,
				identity:"管理员"
			}
		},
		methods:{
			changeShow:function(){
				this.show = !this.show;
				if(this.show == true){
					this.identity = "管理员";
				}
				else {
					this.identity = "普通账户";
				}
			},
			userLogin:function(){
				this.$router.push({ path: '/userpage' });
			},
			adminLogin:function(){
				this.$router.push({ path: '/adminpage' });
			}
		}
	}
</script>

<style>
	#login-container{
		width: 100%;
		height: 100%;
		overflow: hidden;
		background-image: url("../assets/bg3.jpg");
		background-repeat: no-repeat;
		background-size: 100%;
	}
	.login-font{
		width: 330px;
		margin: 180px auto 0 auto;
		font-family: "Hiragino Sans GB","Microsoft YaHei","微软雅黑",tahoma,arial,simsun,"宋体";
	}
	.login-font p{
		font-size: 96px;
		margin: 0;
		padding: 0;
		color: #FFFFFF;
		font-weight: 300;
	}
	.login-center{
		width: 600px;
		height: 350px;
		margin: 20px auto;
		overflow: hidden;
		background-color: rgba(248,248,255,0.2);
	}
	.login-user{
		width: 45%;
		margin: 80px auto 60px auto;
		color: #f5f5f5;
	}
	.login-admin{
		width: 60%;
		margin: 80px auto 60px auto;
		color: #f5f5f5;
	}
	.psd-set{
		margin-top: 40px;
	}
	.login-input{
		border-radius: 4px;
		border:none;
		width: 200px;
		height: 25px;
		background-color: rgba(255,255,255,0.7);
	}
	.btn-submit{
		width: 160px;
		height: 35px;
		display: block;
		margin: 45px auto;
		background-color: #7EA910;
		border: none;
		color: white;
		font-size: 18px;
	}
	.btn-submit:hover{
		cursor: pointer;
		background-color: rgb(174,213,23)
	}
	.btn-submit:active{
		color:rgba(250,128,114,0.7);;
	}
	.btn-submit:focus{
		outline:none;
	}
	.login-choose{
		margin-left: 68%;
		font-size: 16px;
		color:#1D8CE0;
	}
	.login-choose:hover{
		cursor: pointer;
		color:#20A0FF;
	}
</style>
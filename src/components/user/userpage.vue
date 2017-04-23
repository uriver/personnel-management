<template>
	<div id="user-container">
		<header>	
			<el-menu theme="dark" :default-active="activeIndex" class="nav" mode="horizontal" @select="handleSelect" router="true" >
				<router-link to='/userpage'><el-menu-item class="logo"><img src="../../assets/logo.png" height="30" width="240"></el-menu-item></router-link>
			    <el-menu-item index="/userpage" class="nav-margin">主页</el-menu-item>
			    <el-submenu index="">
				    <template slot="title">周报</template>
				    <el-menu-item index="/userpage/weekly-sub">周报提交</el-menu-item>
				    <el-menu-item index="/userpage/weekly-check">周报审核</el-menu-item>
				    <el-menu-item index="/userpage/weekly-history">已通过审核周报</el-menu-item>
				</el-submenu>
			    <el-menu-item index="/userpage/task">任务查看</el-menu-item>
			    <el-menu-item index="/userpage/user-message">个人信息</el-menu-item>
			</el-menu>
		</header>
		<div class="main-content">
			<router-view>
				
			</router-view>
		</div>
		<footer class="footer">
			<p class="copy">&copy 网络信息安全实验室</p>
			<p class="copy2">地址: 哈尔滨工业大学（威海）</p>
		</footer>
	</div>
</template>

<script>
  export default {
    data() {
      return {
        activeIndex: '/userpage'
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>

<style>
	#user-container{
		width: 100%;
		height: 100%;
		min-height: 900px;
	}
	.logo{
		padding-top: 10px !important;
	}
	.nav-margin{
		margin-left: 180px !important;
	}
	.main-content{
		width: 100%;
		height: calc(100% - 60px);
	}
	.footer{
		width: 100%;
		height: 70px;
		margin-top: -70px;
		text-align: center;
		overflow: hidden;
		background-color: #324157;
	}
	.copy{
		color: #f5f5f5;
		margin-top: 20px;
		font-weight: 300;
		font-size: 14px;
	}
	.copy2{
		color: #f5f5f5;
		margin-top: -10px;
		font-weight: 300;
		font-size: 14px;
	}
</style>
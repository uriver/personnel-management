<template>
	<div id="admin-container">
		<header>	
			<el-menu theme="dark" :default-active="activeIndex" class="nav" mode="horizontal" @select="handleSelect" router="true" >
				<router-link to='/adminpage'><el-menu-item class="logo"><img src="../../assets/logo.png" height="30" width="240"></el-menu-item></router-link>
			    <el-menu-item index="/adminpage">任务查看</el-menu-item>
			    <el-menu-item index="/adminpage/notice">通知发布</el-menu-item>
			</el-menu>
		</header>
		<div class="main-content">
			<router-view>
				
			</router-view>
		</div>
		<div class="foot-margin"></div>
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
        activeIndex: '/adminpage'
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
	#admin-container{
		width: 100%;
		min-height: 900px;
	}
</style>
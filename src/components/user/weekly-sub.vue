<template>
	<div class="user-weekly">
		<div class="week-lr"></div>
		<div class="week-center">
			<div style="margin-top:50px"></div>
			<div>
				<h1>创建周报</h1>
			</div>
			<el-form ref="form" :model="form" label-width="80px">
			  <el-form-item label="周报主题">
			  	<el-col :span="18">
			    <el-input v-model="form.name"></el-input>
				</el-col>
			  </el-form-item>

			  <el-form-item label="工作小组">
			    <el-select v-model="form.region" placeholder="请选择工作小组">
			      <el-option label="云计算小组" value="cloud"></el-option>
			      <el-option label="虚拟化小组" value="dooker"></el-option>
			      <el-option label="DNS解析小组" value="dns"></el-option>
			    </el-select>
			  </el-form-item>

			  <el-form-item label="创建时间">
			    <el-col :span="11">
			      <el-date-picker type="date" placeholder="选择日期" v-model="form.date" style="width: 100%;"></el-date-picker>
			    </el-col>
			  </el-form-item>
				
			  <el-col :span='18'>
			  <el-form-item label="上周总结">
			    <el-input type="textarea" v-model="form.desc1"></el-input>
			  </el-form-item>
			  <el-form-item label="项目进展">
			    <el-input type="textarea" v-model="form.desc2"></el-input>
			  </el-form-item>
			  <el-form-item label="本周计划">
			    <el-input type="textarea" v-model="form.desc3"></el-input>
			  </el-form-item>
			  <el-form-item label="问题汇总">
			    <el-input type="textarea" v-model="form.desc4"></el-input>
			  </el-form-item>
			  </el-col>
			  
			  <el-col>
			  <el-form-item>
			    <el-button type="primary" @click="onSubmit">提交周报</el-button>
			  </el-form-item>
			</el-col>
			</el-form>
		</div>
		<div class="week-lr"></div>
	</div>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          name: '',
          region: '',
          date: '',
          desc1: '',
          desc2: '',
          desc3: '',
          desc4: ''
        }
      }
    },
    methods: {
      onSubmit() {
        console.log('submit!');
      }
    }
  }
</script>

<style>
	.user-weekly{
		width: 100%;
		overflow: hidden;
		display: flex;
	}
	.week-lr{
		flex: 1.2;
	}
	.week-center{
		flex: 4;
	}
	.week-center h1{
		font-size: 34px;
		font-weight: 300;
		margin-bottom: 15px;
	}
	.weekly-line{
		width: 700px;
		height: 60px;
		margin-bottom: 18px;
		border-bottom: 1px solid #BABABA;
	}
</style>
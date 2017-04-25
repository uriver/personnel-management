<template>
	<div class="user-weekly">
		<div class="week-lr"></div>
		<div class="week-center">
			<div style="margin-top:40px"></div>
			<div class="weekly-line"><h1>通知</h1></div>

          <div class="admin-weekly">
            <div class="title-set">通知发布</div>
            <div class="title-intro">编辑和发布通知</div>
            <div class="edit-notice">
              <el-form :model="noticeForm" :rules="noticeRules" ref="noticeForm" label-width="100px">

                <el-form-item label="通知标题" prop="noticeTitle">
                  <el-col :span="12">
                    <el-input v-model="noticeForm.noticeTitle"></el-input>
                </el-col>
                </el-form-item>

                <el-form-item label="通知内容" prop="noticeContent">
                  <el-col :span="20">
                    <el-input type="textarea" :autosize="{ minRows: 4, maxRows: 8}"  v-model="noticeForm.noticeContent"></el-input>
                  </el-col>
                </el-form-item>

                <el-form-item>
                  <el-button type="primary" @click="submitForm('noticeForm')">提交</el-button>
                  <el-button @click="resetForm('noticeForm')">重置</el-button>
                </el-form-item>

              </el-form>
            </div>
        </div>

        <div class="admin-separate"></div>

        <div class="admin-weekly">
          <div class="title-set">通知概览</div>
          <div class="title-intro">查看所有通知数据</div>
  			  <el-table
  			    :data="tableData"
  			    border
  			    style="width: 90%">
  			    <el-table-column
  			      label="日期"
  			      width="200">
  			      <template scope="scope">
  			        <el-icon name="time"></el-icon>
  			        <span style="margin-left: 10px">{{ scope.row.date }}</span>
  			      </template>
  			    </el-table-column>

  			    <el-table-column
  			      label="通知名称"
  			      width="500">
  			      <template scope="scope">
  			        <span>{{ scope.row.theme }}</span>
  			      </template>
  			    </el-table-column>

  			    <el-table-column label="功能">
  			      <template scope="scope">
  			        <el-button type="primary" size="small" @click="openNotice(scope.$index)">查看</el-button>
                <el-button type="danger" size="small">更改</el-button>
  			      </template>
  			    </el-table-column>
  			  </el-table>
      </div>

		</div>
		<div class="week-lr"></div>
	</div>
</template>

<script>
  export default {
    data() {
      return {
        noticeForm:{
          noticeTitle:'',
          noticeContent:''
        },
        noticeRules:{
          noticeTitle: [
            { required: true, message: '请输入通知标题', trigger: 'blur' },
          ],
          noticeContent:[
            { required: true, message: '请填写通知内容', trigger: 'blur' }
          ]
        },
        tableData: []
      }
    },
    mounted:function(){
      this.getData();
    },
    methods: {
      getData:function(){
        var self = this;
        this.$http.get("/static/notice.json").then(function(res){
          self.tableData = res.data;
        })
      },
      openNotice(scope) {
        this.$msgbox({
          title: this.tableData[scope].theme,
          message: this.tableData[scope].content,
          confirmButtonText: '确定',
        })
      },
      handleEdit(index, row) {
        console.log(index, row);
      },
      handleDelete(index, row) {
        console.log(index, row);
      },
      submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
            alert('submit!');
          } else {
            console.log('error submit!!');
            return false;
          }
        });
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      }
    }
  }
</script>

<style>
</style>
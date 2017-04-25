<template>
	<div class="user-weekly">
		<div class="week-lr"></div>
		<div class="week-center">
			<div style="margin-top:40px"></div>
			<div class="weekly-line"><h1>主页开发中……</h1></div>

          <div class="admin-weekly">
            <div class="title-set">通知查看</div>
            <div class="title-intro">查看通知列表</div>
            <el-table
              :data="noticeData"
              border
              style="width: 70%">
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
                width="400">
                <template scope="scope">
                  <span>{{ scope.row.theme }}</span>
                </template>
              </el-table-column>

              <el-table-column
                label="功能">
                <template scope="scope">
                  <el-button type="success" size="small" @click="openNotice(scope.$index)">查看</el-button>
                </template>
              </el-table-column>

            </el-table>
        </div>

        <div class="admin-separate"></div>

        <div class="admin-weekly">
          <div class="title-set">操作概览</div>
          <div class="title-intro">查看所有操作记录</div>
  			  <el-table
  			    :data="operateData"
  			    border
  			    style="width: 100%">
  			    <el-table-column
  			      label="日期"
  			      width="200">
  			      <template scope="scope">
  			        <el-icon name="time"></el-icon>
  			        <span style="margin-left: 10px">{{ scope.row.date }}</span>
  			      </template>
  			    </el-table-column>

  			    <el-table-column
  			      label="操作者"
  			      width="180">
  			      <template scope="scope">
  			        <span>{{ scope.row.operator }}</span>
  			      </template>
  			    </el-table-column>

  			    <el-table-column
  			      label="操作名称"
  			      width="400">
  			      <template scope="scope">
  			        <span>{{ scope.row.title }}</span>
  			      </template>
  			    </el-table-column>

            <el-table-column
                label="功能"
                width="200">
                <template scope="scope">
                  <el-button size="small">查看</el-button>
                </template>
              </el-table-column>
<!-- scope.row.status === '未通过' ? 'primary' : 'success' -->
  			    <el-table-column label="当前结果">
  			      <template scope="scope">
  			        <el-tag :type="scope.row.statusJudge" size="small">{{scope.row.status}}
                </el-tag>
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
        noticeData: [],
        operateData:[]
      }
    },
    mounted:function(){
      this.getNoticeData();
      this.getWeeklyData();
    },
    methods: {
      getNoticeData:function(){
        var self = this;
        this.$http.get("/static/notice.json").then(function(res){
          self.noticeData = res.data;
        })
      },
      getWeeklyData:function(){
        var self = this;
        this.$http.get("/static/operate.json").then(function(res){
          console.log(res.data.events);
          self.operateData = res.data.events;
        })
      },
      openNotice(scope) {
        this.$msgbox({
          title: this.noticeData[scope].theme,
          message: this.noticeData[scope].content,
          confirmButtonText: '确定',
      	})
      },
      handleEdit(index, row) {
        console.log(index, row);
      },
      handleDelete(index, row) {
        console.log(index, row);
      }
    }
  }
</script>

<style>
  .admin-weekly{

  }
  .title-set{
    margin-bottom: 8px;
    font-size: 22px;
  }
  .title-intro{
    margin-bottom: 15px;
    font-size: 14px;
    color: #5e6d82;
  }
  .admin-separate{
    height: 40px
  }
</style>
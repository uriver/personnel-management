<template>
	<div class="user-weekly">
		<div class="week-lr"></div>
		<div class="week-center">
			<div style="margin-top:40px"></div>
			<div class="weekly-line"><h1>任务查看</h1></div>

          <div class="admin-weekly">
            <div class="title-set">信息审核</div>
            <div class="title-intro">查看或处理个人信息改动数据</div>
            <el-table
              :data="tableData"
              border
              style="width: 85%">
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
                  <span>{{ scope.row.name }}</span>
                </template>
              </el-table-column>

              <el-table-column
                label="功能"
                width="300">
                <template scope="scope">
                  <el-button size="small">查看</el-button>
                </template>
              </el-table-column>

              <el-table-column label="处理">
                <template scope="scope">
                  <el-button type="primary" size="small">通过</el-button>
                  <el-button type="danger" size="small">驳回</el-button>
                </template>
              </el-table-column>
            </el-table>
        </div>

        <div class="admin-separate"></div>

        <div class="admin-weekly">
          <div class="title-set">周报概览</div>
          <div class="title-intro">查看所有周报数据</div>
  			  <el-table
  			    :data="tableData"
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
  			        <span>{{ scope.row.name }}</span>
  			      </template>
  			    </el-table-column>

  			    <el-table-column
  			      label="操作名称"
  			      width="500">
  			      <template scope="scope">
  			        <span>{{ scope.row.theme }}</span>
  			      </template>
  			    </el-table-column>

  			    <el-table-column label="当前结果">
  			      <template scope="scope">
  			        <el-tag type="primary" size="small">通过</el-tag>
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
        tableData: [{
          date: '2016-05-02',
          name: '张三',
          theme: '2017年4月第一周周报汇报'
        }, {
          date: '2016-05-04',
          name: '李四',
          theme: '2017年5月第一周周报汇报'
        }, {
          date: '2016-05-01',
          name: '王五',
          theme: '2017年5月第一周周报汇报'
        }, {
          date: '2016-05-01',
          name: '王五',
          theme: '2017年5月第一周周报汇报'
        }, {
          date: '2016-05-01',
          name: '王五',
          theme: '2017年5月第一周周报汇报'
        }, {
          date: '2016-05-01',
          name: '王五',
          theme: '2017年5月第一周周报汇报'
        }, {
          date: '2016-05-01',
          name: '王五',
          theme: '2017年5月第一周周报汇报'
        },{
          date: '2016-05-03',
          name: '赵六',
          theme: '2017年5月第一周周报汇报'
        }]
      }
    },
    methods: {
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
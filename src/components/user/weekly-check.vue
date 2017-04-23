<template>
	<div class="user-weekly">
		<div class="week-lr"></div>
		<div class="week-center">
			<div style="margin-top:80px"></div>
			<div class="weekly-line"><h1>周报审核</h1></div>
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
			      label="提交人"
			      width="180">
			      <template scope="scope">
			        <span>{{ scope.row.name }}</span>
			      </template>
			    </el-table-column>

			    <el-table-column
			      label="周报主题"
			      width="400">
			      <template scope="scope">
			        <span>{{ scope.row.theme }}</span>
			      </template>
			    </el-table-column>

			    <el-table-column label="操作">
			      <template scope="scope">
			        <el-button size="small">查看</el-button>
			        <el-button type="primary" size="small">通过</el-button>
			        <el-button type="danger" size="small">驳回</el-button>
			      </template>
			    </el-table-column>
			  </el-table>
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
</style>
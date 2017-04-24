<template>
	<div class="umess-container">
		<div class="umess-lr">
		</div>
		<div class="umess-center">
			<div style="margin-top:50px"></div>
			<div class="weekly-line">
				<h1>修改信息</h1>
			</div>
			
			<div class="cgmessage">
				<el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="100px">

				  <el-form-item label="姓名" prop="name">
				  	<el-col :span="8">
				    	<el-input v-model="ruleForm.name"></el-input>
					</el-col>
				  </el-form-item>
					
				<el-form-item label="性别" prop="sex">
				    <el-radio-group v-model="ruleForm.sex">
				      <el-radio label="男"></el-radio>
				      <el-radio label="女"></el-radio>
				    </el-radio-group>
				  </el-form-item>

				  <el-form-item label="学号" prop="sid">
				  	<el-col :span="8">
				    	<el-input v-model="ruleForm.id"></el-input>
					</el-col>
				  </el-form-item>

				  <el-form-item label="年级" prop="grade">
				    <el-select v-model="ruleForm.grade" placeholder="请选择年级">
				      <el-option label="大一" value="grade1"></el-option>
				      <el-option label="大二" value="grade2"></el-option>
				      <el-option label="大三" value="grade3"></el-option>
				      <el-option label="大四" value="grade4"></el-option>
				    </el-select>
				  </el-form-item>

				  <el-form-item label="专业" prop="major">
				  	<el-col :span="8">
				    	<el-input v-model="ruleForm.major"></el-input>
					</el-col>
				  </el-form-item>

				  <el-form-item label="邮箱" prop="email">
				  	<el-col :span="8">
				    	<el-input v-model="ruleForm.email"></el-input>
					</el-col>
				  </el-form-item>

				  <el-form-item label="QQ" prop="qq">
				  	<el-col :span="8">
				    	<el-input v-model="ruleForm.qq"></el-input>
					</el-col>
				  </el-form-item>

				  <el-form-item label="手机号" prop="tel">
				  	<el-col :span="8">
				    	<el-input v-model="ruleForm.tel"></el-input>
					</el-col>
				  </el-form-item>

				  <el-form-item label="辅导员" prop="instructor">
				  	<el-col :span="8">
				    	<el-input v-model="ruleForm.instructor"></el-input>
					</el-col>
				  </el-form-item>

				  <el-form-item label="研究室" prop="resOffice">
				    <el-select v-model="ruleForm.office" placeholder="请选择研究室">
				      <el-option label="328研究室" value="resoffice1"></el-option>
				      <el-option label="329研究室" value="resoffice2"></el-option>
				      <el-option label="330研究室" value="resoffice3"></el-option>
				    </el-select>
				  </el-form-item>

				  <el-form-item label="是否退出" prop="exit">
				    <el-radio-group v-model="ruleForm.exit">
				      <el-radio label="是"></el-radio>
				      <el-radio label="否"></el-radio>
				    </el-radio-group>
				  </el-form-item>

				  <el-form-item label="出生日期" required>
				    <el-col :span="8">
				      <el-form-item prop="date">
				        <el-date-picker type="date" placeholder="出生日期" v-model="ruleForm.date" style="width: 100%;"></el-date-picker>
				      </el-form-item>
				    </el-col>
				  </el-form-item>

				  <el-form-item label="身份证号" prop="instructor">
				  	<el-col :span="8">
				    	<el-input v-model="ruleForm.instructor"></el-input>
					</el-col>
				  </el-form-item>
					
				  <div>
					
				  </div>

				  <el-form-item label="实验室小组" prop="group">
				    <el-select v-model="ruleForm.group" placeholder="请选择实验室小组">
				      <el-option label="云计算组" value="group11"></el-option>
				      <el-option label="虚拟化组" value="group2"></el-option>
				      <el-option label="攻防组" value="group3"></el-option>
				    </el-select>
				  </el-form-item>

				  <el-form-item label="所在办公室" prop="office">
				    <el-select v-model="ruleForm.group" placeholder="请选择实验室小组">
				      <el-option label="330办公室" value="office1"></el-option>
				      <el-option label="331办公室" value="office2"></el-option>
				      <el-option label="攻防组" value="office3"></el-option>
				    </el-select>
				  </el-form-item>

				  <el-form-item label="加入中心时间" prop="joinTime">
				  	<el-col :span="8">
				    	<el-input v-model="ruleForm.joinTime"></el-input>
					</el-col>
				  </el-form-item>

				  <el-form-item label="紧急联系人" prop="emergencyContact">
				  	<el-col :span="8">
				    	<el-input v-model="ruleForm.emergencyContact"></el-input>
					</el-col>
				  </el-form-item>

				  <el-form-item label="紧急联系电话" prop="emergencyTelephone">
				  	<el-col :span="8">
				    	<el-input v-model="ruleForm.emergencyTelephone"></el-input>
					</el-col>
				  </el-form-item>

				  <el-form-item>
				    <el-button type="primary" @click="submitForm('ruleForm')">提交</el-button>
				    <el-button @click="resetForm('ruleForm')">重置</el-button>
				  </el-form-item>
				</el-form>
			</div>

		</div>
		<div class="umess-lr"></div>
	</div>
</template>

<script>
  export default {
    data() {
      return {
        ruleForm: {
          name: '',
          sex: '',
          sid:'',
          grade: '',
          major:'',
          email:'',
          qq:'',
          tel:'',
          instructor:'',
          resOffice:'',
          exit:'',
          date: '',
          id:'',
          group:'',
          office:'',
          joinTime:'',
          emergencyContact:'',
          emergencyTelephone:''
        },
        rules: {
          name: [
            { required: true, message: '请输入姓名', trigger: 'blur' },
            { min: 2, max: 5, message: '长度在 2 到 5 个字符', trigger: 'blur' }
          ],
          sex: [
            { required: true, message: '请选择性别', trigger: 'change' }
          ],
          sid: [
            { required: true, message: '请输入学号', trigger: 'blur' },
            { min: 2, max: 5, message: '长度为7个字符', trigger: 'blur' }
          ],
          grade: [
            { required: true, message: '请选择年级', trigger: 'change' }
          ],
          major: [
            { required: true, message: '请输入专业', trigger: 'blur' }
          ],
          email: [
            { required: true, message: '请输入邮箱', trigger: 'blur' }
          ],
          qq: [
            { required: true, message: '请输入QQ账号', trigger: 'blur' }
          ],
          tel: [
            { required: true, message: '请输入手机号', trigger: 'blur' }
          ],
          instructor: [
            { required: true, message: '请输入辅导员姓名', trigger: 'blur' }
          ],
          resOffice: [
            { required: true, message: '请选择研究室', trigger: 'change' }
          ],
          exit: [
            { required: true, message: '请选择是否退出', trigger: 'change' }
          ],
          date: [
            { type: 'date', required: true, message: '请选择日期', trigger: 'change' }
          ],
          id: [
            { required: true, message: '请输入身份证号', trigger: 'blur' }
          ]
        }
      };
    },
    methods: {
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
	.cgmessage{
		padding-left: 30px;
	}
</style>
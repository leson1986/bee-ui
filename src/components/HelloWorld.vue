<template>
  <div class="hello">
      <div class="box-card">
        <el-row>
            <el-col :span="24">
                <img src="../assets/img/beeUi_mini_Logo.png">
            </el-col>
            <el-col :span="24">
                <h3 style="font-size: 28px">BEE</h3>
            </el-col>
            <el-col :span="24">
                BEE，辛勤的小蜜蜂<br>轻量、可靠、开源的PC端商业应用 Vue 组件库
            </el-col>
        </el-row>
    </div>
    <!-- <info></info> -->
  </div>
</template>

<script type="text/babel">
//   import info from '@/docs/icon.md/'; // 导入md文件
  export default {
    name: 'HelloWorld',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App'
      }
    },
    components:{
    //   info // 注册组件
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.box-card {
    text-align: center;
    padding: 10px;
    margin-top: 25vh;
}
.box-card .el-col {
    padding: 10px;
    line-height: 28px;
}
</style>

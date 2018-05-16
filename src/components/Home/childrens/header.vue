<template>
  <div class="header">
    
    <el-header style="font-size: 12px">
      <span class="logo">Logo</span>
      <span class="el-icon-menu menu_btn" @click="changeCollapse"></span>
      <el-dropdown style="float: right;">
        <i class="el-icon-setting" style="margin-right: 15px"></i>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item>查看</el-dropdown-item>
          <el-dropdown-item>新增</el-dropdown-item>
          <el-dropdown-item>删除</el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
      <span style="float: right;margin-right: 20px;">王小虎</span>
    </el-header>
  </div>
</template>
<script>
import bus from '@/common/Bus/bus'
export default {
  name: 'HomeHeader',
  data () {
    return {
      isCollapse: false
    }
  },
  methods: {
    changeCollapse () {
      this.isCollapse = !this.isCollapse
      // this.$emit('changeCollapse',this.isCollapse)
      bus.$emit('changeisCollapse',this.isCollapse)
      console.log(this.isCollapse)
    }
  }
}
</script>
<style scoped>
  .header{
    width: 100%;
    /* position: fixed; */
  }
  .logo{
    display: inline-block;
    width: 190px;
  }
  .menu_btn{
    font-size: 18px;
    padding: 21px 10px;
    cursor: pointer;
  }
</style>

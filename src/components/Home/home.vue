<template>
  <div class="home">
    <el-container>
      <home-header></home-header>
    </el-container>
    <el-container style="height: 100vh; border: 1px solid #eee;" class="box">
      <home-left-nav></home-left-nav>
      <home-main></home-main>
    <!-- <home-header></home-header> -->
    </el-container>
  </div>  
</template>

<script>
import HomeHeader from './childrens/header'
import HomeMain from './childrens/main'
import HomeLeftNav from './childrens/left_nav'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeMain,
    HomeLeftNav
  },
  data () {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .box{
    position: fixed;
    top: 60px;
    left: 0;
    right: 0;
  }
  .el-header {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
  }
  
  .el-aside {
    color: #333;
    border-right: solid 1px #e6e6e6;
  }
  .el-menu {
    border: none;
  }
</style>
<template>
  <el-container class="main">
  <!-- <home-header></home-header> -->
    
    <el-main>
      <el-table :data="tableData">
        <el-table-column prop="date" label="日期" width="140">
        </el-table-column>
        <el-table-column prop="name" label="姓名" width="120">
        </el-table-column>
        <el-table-column prop="address" label="地址">
        </el-table-column>
        <el-table-column prop="" label="操作">
          <template slot-scope="scope">
            <el-button @click="handleClick(scope.row)" type="text" size="small">查看</el-button>
            <el-button type="text" size="small">编辑</el-button>
          </template>
        </el-table-column>
      </el-table>
    </el-main>
    <home-form v-show="showForm"></home-form>
  </el-container>
</template>
<script>
import bus from '@/common/Bus/bus'
import HomeForm from '../../Form/HomeForm'
export default {
  name: 'HomeMain',
  components: {
    HomeForm
  },
  data() {
    const item = {
      date: '2016-05-02',
      name: '王小虎',
      address: '上海市普陀区金沙江路 1518 弄'
    };
    return {
      tableData: Array(20).fill(item),
      showForm: false
    }
  },
  created () {
    bus.$on('HideHomeForm',(statu) => {
      this.showForm = false
    })
  },
  methods: {
    handleClick (a) {
      console.log(a)
      this.showForm = true
      bus.$emit('ShowHomeForm',true)    
      console.log(this.showForm)
    }
  }
}
</script>
<style scoped>
  .main {
    /* min-width: 824px; */
  }
</style>
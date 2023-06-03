<template>
  <div style="padding: 10px">
<!--    功能区-->
    <div style="margin: 10px 0">
<el-button type="primary">添加</el-button>
<el-button type="primary">导出</el-button>
<el-button type="primary">历史数据</el-button>
<el-button type="primary">名号</el-button>
<el-button type="primary">密码</el-button>
    </div>
<!--    搜索区-->
    <div style="margin: 10px 0">
      <el-input v-model="search" placeholder="请输入关键字" style="width: 300px" />
      <el-button type="primary" style="margin-left: 5px">查询</el-button>
    </div>
<!--<el-button></el-button>-->
    <el-table :data="tableData" border stripe   style="width: 100%">
      <el-table-column prop="date" label="Date" sortable  />
      <el-table-column prop="name" label="Name"  />
      <el-table-column prop="address" label="Address" />
      <el-table-column fixed="right" label="操作" width="120">
        <template #default>
          <el-button link type="primary" size="small" @click="handleClick">查看</el-button>
          <el-popconfirm title="确认删除么?">
            <template #reference>
              <el-button link type="primary" size="small">删除</el-button>
            </template>
          </el-popconfirm>

        </template>
      </el-table-column>
    </el-table>
    <div style="padding: 10px 0">
      <el-pagination
          v-model:current-page="currentPage4"
          v-model:page-size="pageSize4"
          :page-sizes="[10, 20, 30]"
          :small="small"
          :disabled="disabled"
          :background="background"
          layout="total, sizes, prev, pager, next, jumper"
          :total="100"
          @size-change="handleSizeChange"
          @current-change="handleCurrentChange"
      />
    </div>

  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {

  },
  data(){
    return{
      search:'',
      currentPage4:'',
      pageSize4:'',
      tableData:[
          {
        date: '2016-05-03',
        name: 'Tom',
        address: 'No. 189, Grove St, Los Angeles',
      },
        {
          date: '2016-05-02',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
        },
        {
          date: '2016-05-04',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
        },
        {
          date: '2016-05-01',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
        },
      ]
    }
  },
  methods:{
    handleClick(){

    },
    handleSizeChange(){

    },
    handleCurrentChange(){

    }
  }
}
</script>

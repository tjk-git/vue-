<script setup>

</script>

<template>
  <div style="height: 50px;line-height: 50px;border-bottom: 1px solid #ccc;display: flex ">
    <div style="width: 300px;padding-left: 50px;font-weight: bold;color: aqua">后台管理</div>
    <div style="flex:1"></div>
    <div style="width: 100px;padding-top: 17px">
      <el-dropdown>
    <span class="el-dropdown-link">
      故障设备数
      <el-icon class="el-icon--right">
        <arrow-down />
      </el-icon>
    </span>
          <template #dropdown>
            <el-dropdown-menu>
              <el-dropdown-item>Action 1</el-dropdown-item>
              <el-dropdown-item>Action 2</el-dropdown-item>
              <el-dropdown-item>Action 3</el-dropdown-item>
              <el-dropdown-item disabled>Action 4</el-dropdown-item>
              <el-dropdown-item divided>Action 5</el-dropdown-item>
            </el-dropdown-menu>
          </template>
        </el-dropdown>
    </div>
  </div>
</template>


<script>
export default {
  name: "Header",
}
</script>
<style scoped>

</style>
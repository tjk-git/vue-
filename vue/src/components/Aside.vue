<script setup>

</script>

<template>
  <div>
    <el-row class="tac">
      <el-col :span="12">
<!--        <h5 class="mb-2">列表</h5>-->
        <el-menu
            style="width: 200px"
            class="el-menu-vertical-demo"
            default-active="home"
            router >
        <el-sub-menu index="1">
          <template #title>
            <el-icon>
              <location/>
            </el-icon>
            <span>一</span>
          </template>
          <el-menu-item-group title="Group One">
            <el-menu-item index="home">item one</el-menu-item>
            <el-menu-item index="/">item two</el-menu-item>
          </el-menu-item-group>
          <el-menu-item-group title="Group Two">
            <el-menu-item index="1-3">item three</el-menu-item>
          </el-menu-item-group>
          <el-sub-menu index="1-4">
            <template #title>item four</template>
            <el-menu-item index="1-4-1">item one</el-menu-item>
          </el-sub-menu>
        </el-sub-menu>
        <el-menu-item index="2">
          <el-icon>
            <icon-menu/>
          </el-icon>
          <span>二</span>
        </el-menu-item>
        <el-menu-item disabled index="3">
          <el-icon>
            <document/>
          </el-icon>
          <span>三</span>
        </el-menu-item>
        <el-menu-item index="4">
          <el-icon>
            <setting/>
          </el-icon>
          <span>四 </span>
        </el-menu-item>
        </el-menu>
      </el-col>

    </el-row>
  </div>
</template>

<script>
export default {
  name: "Aside",
}
</script>
<style scoped>

</style>
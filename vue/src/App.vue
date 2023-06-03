<template>
  <div>
<!--头部-->
    <Header />
<!--    主体-->
    <div style="display: flex">
<!--      侧边栏-->
     <Aside />
<!--内容-->
      <router-view style="flex: 1"/>
    </div>
  </div>

</template>


<script>


import Header from "@/components/header.vue";
import Aside from "@/components/Aside.vue";


export default {
  name:"layout",
  components:{
    Header,
    Aside,
  }
}
</script>


<style>

</style>

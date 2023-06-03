


<template>
  <div class="common-layout">
    <el-container >
      <el-aside height="1320px" width="60px">地图</el-aside>
      <div >
        <img src="../assets/logo.png" alt="">
      </div>
      <el-container>
        <el-header height="30px">Header</el-header>
        <el-row :gutter="40">
          <el-col :span="6">当前设备数量<div style="height: 100px" class="grid-content ep-bg-purple" /></el-col>
          <el-col :span="6">RSU设备数<div class="grid-content ep-bg-purple" /></el-col>
          <el-col :span="6">故障设备数<div class="grid-content ep-bg-purple" /></el-col>
          <el-col :span="6"><div class="grid-content ep-bg-purple" /></el-col>
        </el-row>
        <el-main>Main</el-main>
        <div
            class="echart"
            ref="mychart2"
            style="height:400px"
        >

        </div>
      </el-container>
    </el-container>
  </div>
<!--  <div  style="height: 50px;line-height: 50px; ">-->
<!--    <h1>主页11</h1>-->
<!--  </div>-->



</template>

<script>
import * as echarts from "echarts";

export default {
  name: 'EchartsBar2',
  data () {
    return {}
  },
  mounted () {
    this.initBar()
  },
  methods: {
    initBar () {
      const option = {
        title: { // 标题组件
          text: '效果柱状图',
          top: 20,
          left: 'center', // 距离容器左侧的距离。可选left,right等
          textStyle: {
            color: '#fff',
            fontSize: 25
          }
        },
        grid: { // 直角坐标系内绘图网格
          containLabel: false,
          bottom: '10%',// grid 组件离容器下侧的距离。默认60px
          top: '20%' // grid 组件离容器上侧的距离。默认60px
        },
        xAxis: { // X轴-相关设置
          axisLabel: { // X轴-坐标轴刻度标签的相关设置。
            show: true, // 是否显示刻度标签。默认为true
            color: '#fff',
            rotate: 0,// 刻度标签旋转的角度。默认为0
            margin: 20, // 刻度标签与轴线之间的距离。 默认8px
            fontSize: 15,
            // 坐标轴刻度标签的显示间隔。0表示显示所有标签,1表示隔一个标签显示一个标签
            interval: 0
          },
          axisTick: { // X轴-坐标轴刻度相关设置
            show: false
          },
          splitLine: { // X轴-分隔线
            show: false
          },
          axisLine: { // X轴-坐标轴轴线相关设置
            show: true,
            lineStyle: {
              color: '#384267',
              type: 'dashed' // 线的类型。可选'solid'等
            }
          },
          data: ['周一', '周二', '周三', '周四', '周五'],
        },
        yAxis: { // Y轴-相关设置
          name: '车流量', // Y轴-坐标轴名称
          nameTextStyle: { // Y轴-坐标轴名称的文字样式
            color: '#fff',
            padding: [0, 0, 10, 0],
            fontSize: 14
          },
          axisLabel: { // Y轴-坐标轴刻度标签的相关设置
            color: '#fff',
            fontSize: 15,
          },
          axisTick: { // Y轴-坐标轴刻度相关设置。
            show: true,
            lineStyle: {
              color: '#384267'
            }
          },
          splitLine: { // Y轴-分隔线
            show: true,
            lineStyle: {
              color: '#384267',
              type: 'dashed'
            }
          },
          axisLine: { // Y轴-坐标轴轴线相关设置。
            show: true,
            lineStyle: {
              color: '#384267',
              type: 'solid'
            }
          }
        },
        series: [
          { // 柱底
            data: [1000, 750, 850, 500, 233],
            type: 'pictorialBar', // 象形柱图
            //图形的定位位置。柱子开始的地方。可选start,end,center
            symbolPosition: 'start',
            symbol: 'diamond', //图形类型。可选'circle','rect'等
            // 把图形向下移动了自身尺寸的一半的位置
            symbolOffset: [0, '50%'],
            symbolSize: [30, 15], // 图形的大小
            itemStyle: {
              color: '#02D7EA'
            }
          },
          { // 柱体系列数据
            name: '车流量',
            data: [1000, 750, 850, 500, 233],
            type: 'bar',
            barWidth: 30,
            itemStyle: {
              color: {
                type: 'linear',
                x: 0,
                y: 0,
                x2: 0,
                y2: 1,
                global: false,
                colorStops: [
                  { offset: 0, color: '#057DFE' },// 0% 处的颜色
                  { offset: 1, color: '#02D7EA' }// 100% 处的颜色
                ]
              }
            },
            label: { // 图形上的文本标签
              show: true,
              position: 'top', // 标签的位置。可选top，left等
              distance: 10, // 距离图形元素的距离。默认值5
              color: '#fff'
            }
          },
          { // 柱顶
            data: [1000, 750, 850, 500, 233],
            type: 'pictorialBar', // 象形柱图
            //图形的定位位置。柱子结束的地方。可选start,end,center
            symbolPosition: 'end',
            symbol: 'diamond', //图形类型。可选'circle','rect'等
            // 把图形向上移动了自身尺寸的一半的位置。
            symbolOffset: [0, '-50%'],
            symbolSize: [30, 15], // 图形的大小
            itemStyle: {
              color: {
                type: 'linear',
                x: 0,
                y: 0,
                x2: 0,
                y2: 1,
                global: false,
                colorStops: [
                  { offset: 0, color: '#057DFE' },// 0% 处的颜色
                  { offset: 1, color: '#02D7EA' }// 100% 处的颜色
                ]
              }
            },
            z: 3
          }
        ],
        tooltip: {
          trigger: 'axis',
          backgroundColor: 'rgba(17,95,182,0.5)',
          textStyle: {
            color: '#fff'
          },
          axisPointer: {
            type: 'shadow'
          },
          formatter: (params) => {
            return (
                `${params[0].name}<br />
              ${params[0].seriesName}：${params[0].value}`
            )
          }
        },
      }
      const myChart = echarts.init(this.$refs['mychart2'])
      myChart.setOption(option)
    }
  }
}

</script>

<style>

html,
body {
  height: 100%;
  width: 100%;
  padding: 0;
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #F0E90C;
  background: #28AEAE;
  height: 100%;
  width: 100%;
  overflow-x: hidden;
}
.echarts-wrap {
  height: 100%;
  width: 100%;
  display: flex;
  flex-wrap: wrap;
}
.echarts-item {
  width: 50%;
}
</style>
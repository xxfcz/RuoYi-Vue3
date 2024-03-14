<script setup>
import {onMounted, ref} from "vue";
import {init} from "echarts";

// 声明一个与 ref 属性名称相同的变量
const elChart = ref(null);

onMounted(() => {
  // 通过 elChart.value 的形式取到 DOM 元素
  const myChart = init(elChart.value);
  const option = {
    xAxis: {
      type: 'category',
      data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
    },
    yAxis: {
      type: 'value'
    },
    series: [
      {
        data: [150, 230, 224, 218, 135, 147, 260],
        type: 'bar'
      }
    ]
  };
  myChart.setOption(option);
});
</script>

<template>
  <div>ECharts 图表示例</div>
  <div ref="elChart" style="width: 800px; height: 600px"></div>
</template>

<style scoped lang="scss">

</style>
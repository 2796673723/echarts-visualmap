<template>
  <div id="app">
    <div ref="chart" class="chart"></div>
  </div>
</template>

<script>
import * as echarts from "echarts";
export default {
  mounted() {
    const chart = echarts.init(this.$refs.chart);
    chart.setOption({
      xAxis: {
        type: "category",
        data: ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"],
      },
      yAxis: {
        type: "value",
      },
      series: [
        {
          data: [150, 140, 140, 0, 0, 0, 0],
          type: "line",
        },
      ],
      visualMap: {
        show: false,
        pieces: [
          {
            gte: 0, //it has the same reuslt when use 'gt'
            lte: 140,
            color: "#4A90E2",
          },
        ],
        outOfRange: { color: "#FF0000" },
      },
    });
  },
};
</script>
<style>
body {
  padding: 0px;
  margin: 0px;
}
.chart {
  height: 100vh;
  width: 100%;
}
</style>

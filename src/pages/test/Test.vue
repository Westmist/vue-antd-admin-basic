<template>
  <div id="test">
    <div id="echarts"></div>
  </div>
</template>
<script>
import Chart from "echarts";
export default {
  name: "Test",
  data() {
    return {
      echarts: null,
    };
  },
  methods: {
    initEcharts() {
      let option = {
        xAxis: {
          type: "category",
          data: ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"],
        },
        yAxis: {
          type: "value",
        },
        series: [
          {
            data: [150, 230, 224, 218, 135, 147, 260],
            type: "line",
          },
        ],
      };
      this.echarts.setOption(option);
    },
  },
  mounted() {
    this.echarts = Chart.init(document.getElementById("echarts"));
    this.initEcharts();
  },

};
</script>
<style scoped>
#echarts {
  width: 90%;
  /*  高度不能为100% */
  height: 600px;
}
</style>

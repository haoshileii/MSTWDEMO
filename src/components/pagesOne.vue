<template>
  <div>
    <div ref="barChart" style="width: 600px; height: 400px"></div>
    <div ref="heatmap" style="width: 600px; height: 400px"></div>
  </div>
</template>
<script>
import * as echarts from "echarts";
export default {
  name: "ChartComponent",
  data() {
    return {
      barChart: null,
      heatmap: null,
    };
  },
  mounted() {
    this.initBarChart();
    this.initHeatmap();
  },
  methods: {
    initBarChart() {
      this.chart = echarts.init(this.$refs.barChart);
      this.chart.setOption({
        //backgroundColor: "#000", // 设置背景颜色为黑色
        title: {
          text: "示例柱状图",
        },
        tooltip: {},
        xAxis: {
          data: ["方法一", "方法二", "方法三", "方法四", "方法五", "方法六"],
        },
        yAxis: {
          type: "value",
        },
        series: [
          {
            name: "最优数",
            type: "bar",
            data: [5, 20, 36, 10, 10, 20],
          },
        ],
      });
    },
    initHeatmap() {
      this.heatmap = echarts.init(this.$refs.heatmap);
      this.heatmap.setOption({
        title: {
          text: "示例热力图",
          textStyle: { color: "#333" },
        },
        tooltip: {},
        xAxis: {
          type: "category",
          data: [
            "数据集一",
            "数据集二",
            "数据集三",
            "数据集四",
            "数据集五",
            "数据集六",
            "数据集七",
          ],
          splitArea: { show: true },
        },
        yAxis: {
          type: "category",
          data: ["0.3", "0.6", "0.9"],
          splitArea: { show: true },
        },
        visualMap: {
          min: 0,
          max: 10,
          calculable: true,
          orient: "horizontal",
          left: "center",
          bottom: "15%",
        },
        series: [
          {
            name: "准确率",
            type: "heatmap",
            data: [
              [0, 0, 5],
              [0, 1, 7],
              [0, 2, 6],
              [1, 0, 1],
              [1, 1, 1],
              [1, 2, 7],
              [2, 0, 3],
              [2, 1, 2],
              [2, 2, 8],
              [3, 0, 4],
              [3, 1, 6],
              [3, 2, 7],
              [4, 0, 7],
              [4, 1, 8],
              [4, 2, 6],
              [5, 0, 5],
              [5, 1, 3],
              [5, 2, 1],
              [6, 0, 2],
              [6, 1, 4],
              [6, 2, 5],
            ],
            itemStyle: {
              emphasis: { shadowBlur: 10, shadowColor: "rgba(0, 0, 0, 0.5)" },
            },
          },
        ],
      });
    },
  },
  beforeDestroy() {
    if (this.barChart) {
      this.barChart.dispose();
    }
    if (this.heatmap) {
      this.heatmap.dispose();
    }
  },
};
</script>

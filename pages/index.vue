<template>
  <view>
    <echarts
      :option="option"
      style="height: 300px"
      @click="echartsClick"
    ></echarts>
  </view>
</template>

<script>
import Echarts from "@/components/echarts/echarts.vue";
const data = [
  [
    [28604, 77, 17096869, "Australia", 1990],
    [31163, 77.4, 27662440, "Canada", 1990],
    [1516, 68, 1154605773, "China", 1990],
    [13670, 74.7, 10582082, "Cuba", 1990],
    [28599, 75, 4986705, "Finland", 1990],
    [29476, 77.1, 56943299, "France", 1990],
    [31476, 75.4, 78958237, "Germany", 1990],
    [28666, 78.1, 254830, "Iceland", 1990],
    [1777, 57.7, 870601776, "India", 1990],
    [29550, 79.1, 122249285, "Japan", 1990],
    [2076, 67.9, 20194354, "North Korea", 1990],
    [12087, 72, 42972254, "South Korea", 1990],
    [24021, 75.4, 3397534, "New Zealand", 1990],
    [43296, 76.8, 4240375, "Norway", 1990],
    [10088, 70.8, 38195258, "Poland", 1990],
    [19349, 69.6, 147568552, "Russia", 1990],
    [10670, 67.3, 53994605, "Turkey", 1990],
    [26424, 75.7, 57110117, "United Kingdom", 1990],
    [37062, 75.4, 252847810, "United States", 1990],
  ],
  [
    [44056, 81.8, 23968973, "Australia", 2015],
    [43294, 81.7, 35939927, "Canada", 2015],
    [13334, 76.9, 1376048943, "China", 2015],
    [21291, 78.5, 11389562, "Cuba", 2015],
    [38923, 80.8, 5503457, "Finland", 2015],
    [37599, 81.9, 64395345, "France", 2015],
    [44053, 81.1, 80688545, "Germany", 2015],
    [42182, 82.8, 329425, "Iceland", 2015],
    [5903, 66.8, 1311050527, "India", 2015],
    [36162, 83.5, 126573481, "Japan", 2015],
    [1390, 71.4, 25155317, "North Korea", 2015],
    [34644, 80.7, 50293439, "South Korea", 2015],
    [34186, 80.6, 4528526, "New Zealand", 2015],
    [64304, 81.6, 5210967, "Norway", 2015],
    [24787, 77.3, 38611794, "Poland", 2015],
    [23038, 73.13, 143456918, "Russia", 2015],
    [19360, 76.5, 78665830, "Turkey", 2015],
    [38225, 81.4, 64715810, "United Kingdom", 2015],
    [53354, 79.1, 321773631, "United States", 2015],
  ],
];
export default {
  data() {
    return {
      option2: {
        xAxis: {
          splitLine: { show: false },
        },
        yAxis: {
          splitLine: { show: false },
          scale: true,
        },
        grid: {
          left: 40,
          right: 30,
        },
        // series: [
        //   {
        //     name: "1990",
        //     data: data[0],
        //     type: "scatter",
        //     symbolSize: function (data) {
        //       return Math.sqrt(data[2]) / 5e2;
        //     },
        //     emphasis: {
        //       focus: "self",
        //       // itemStyle: {
        //       //   // 高亮时点的颜色。
        //       //   color: "blue",
        //       // },
        //       // label: {
        //       //   show: true,
        //       //   // 高亮时标签的文字。
        //       //   formatter: "This is a emphasis label.",
        //       // },
        //     },
        //     labelLayout: function () {
        //       return {
        //         x: myChart.getWidth() - 100,
        //         moveOverlap: "shiftY",
        //       };
        //     },
        //     labelLine: {
        //       show: true,
        //       length2: 50,
        //       lineStyle: {
        //         color: "#bbb",
        //       },
        //     },
        //     label: {
        //       show: true,
        //       // formatter: function (param) {
        //       //   return param.data[3];
        //       // },
        //       // position: "right",
        //       // minMargin: 2,
        //     },
        //   },
        // ],
        // "title": "A股行业PEG",
        // "desc": "PEG模型:<br><br>是投资成长股的一种常见模型。 <br>PEG=市盈率/净利润增速。即分析企<br>业估值的时候，结合了企业未来的成<br>长性，弥补了传统市盈率投资模型的<br>缺陷。一般来说PEG越低，被低估的<br>可能性越大。具体参数如下：<br><br>预测市盈率：股票最新收盘价/最近<br>预测年度次年的每股收益预测值<br>预测净利润增速：机构研究员对标<br>的一致预测净利润2年复合增长率<br>",
        // "_x": "净利润增速(%)",
        // "_y": "PE",

        series: [
          {
            data: [
              [13.21, 13.51, "基础化工"],
              [-20.23, 11.45, "钢铁"],
              [50.56, 11.99, "有色金属"],
              [13.38, 21.39, "电子"],
              [13.78, 12.86, "家用电器"],
              [18.29, 24.94, "食品饮料"],
              [23.66, 15.65, "纺织服饰"],
              [17.92, 19.22, "轻工制造"],
              [5.29, 27.08, "医药生物"],
              [93, 15.24, "公用事业"],
              [6.15, 14.83, "交通运输"],
              [119.25, 10.49, "房地产"],
              [-2.21, 10.74, "建筑材料"],
              [23.35, 7.08, "建筑装饰"],
              [61.61, 20.63, "电力设备"],
              [40.48, 36.15, "国防军工"],
              [41.88, 32.21, "计算机"],
              [21.44, 21.81, "传媒"],
              [154.6, 13, "通信"],
              [7.6, 3.94, "银行"],
              [3.85, 11.41, "非银金融"],
              [34.33, 22.08, "汽车"],
              [15.61, 24.22, "机械设备"],
              [27.94, 6.64, "煤炭"],
              [42.51, 7.08, "石油石化"],
              [17.65, 20.55, "环保"],
              [20.27, 33.73, "美容护理"],
            ],
            name: "1990",
            type: "scatter",
            symbolSize: 10,
            emphasis: {
              focus: "self",
              blurScope: "coordinateSystem",
            },
            labelLayout: {
              x: "88%",
              moveOverlap: "shiftY",
            },
            labelLine: {
              show: true,
              length2: 200,
              lineStyle: {
                color: "#bbb",
              },
            },
            label: {
              show: true,
              format: "getlinecolor",
              position: "right",
              color: "#bbb",
              minMargin: 2,
              align: "center",
              verticalAlign: "middle",
            },
          },
        ],
      },
    };
  },
  components: {
    Echarts,
  },
  onLoad() {
    this.option = this.option2;
  },
  methods: {
    /**
     * 点击事件
     * @param {Object} params
     */
    echartsClick(params) {
      console.log("点击数据", params);
    },
  },
};
</script>

<style></style>

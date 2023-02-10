<template>
  <div class="common">
    <div id="MyChart5" style="width: 100%; height: 100%" ref="MyChart5"></div>
  </div>
</template>
<script>
import * as echarts from "echarts";
import elementResizeDetectorMaker from "element-resize-detector";
export default {
  mounted() {
    this.drawLine4();
    const erd1 = elementResizeDetectorMaker();
    if (erd1) {
      erd1.listenTo(this.$refs.MyChart5, (element) => {
        this.MyChart5 && this.MyChart5.resize();
      });
    }
    this.$nextTick(() => {
      window.addEventListener("resize", () => {
        this.drawLine4();
      });
    });
  },
  methods: {
    nowSize(val, initWidth = 1920) {
      let nowClientWidth = document.documentElement.clientWidth;
      return val * (nowClientWidth / initWidth);
    },
    drawLine4() {
      this.MyChart5 = echarts.init(document.getElementById("MyChart5"));
      let option = {
        //没有办法直接修改echarts的大小,通过grid来控制echarts的大小
        grid: {
          bottom: "20vh",
          right: "16vh",
          top: "15vh",
        },
        //  grid:{ // 设置图形位置  横纵轴偏移
        //         left: '10%',
        //         top: '17%',
        //         height: '66%',
        //     },
        xAxis: {
          name: "",
          type: "category",
          nameTextStyle: {
            // x轴单位样式
            fontSize: this.nowSize(16),
            color: "rgba(51,51,51,0.3)",
            padding: [0, 0, this.nowSize(-20), this.nowSize(-20)],
            verticalAlign: "bottom",
          },
          boundaryGap: true,
          data: [
            0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18,
            19, 20, 21, 22, 23, 24,
          ],
          axisLine: {
            lineStyle: {
              color: "rgba(25,22,22,1)",
            },
          },
          axisTick: {
            alignWithLabel: true,
            lineStyle: {
              color: "rgba(256,22,22,1)",
            },
          },
          // x轴下方的文字
          axisLabel: {
            show: true,
            interval: 1,
            fontSize: this.nowSize(16),
            color: "rgba(256,22,22,1)",
          },
        },
        tooltip: {
          trigger: "axis",
          backgroundColor: "#FFF",
          extraCssText: "box-shadow:0px 0px 8px #ddd",
          textStyle: {
            color: "#959595",
          },
          formatter: (params, index) => {
            // console.log(params,'ooooo')
            let title =
              '<div style="line-height:32px;margin-left:8px;margin-right:8px">' +
              params[0].axisValue;

            let result = "";
            params.forEach((element, index) => {
              result +=
                '<div style="line-height:28px;margin-left:8px;margin-right:8px"><div style="margin-right:6px;float:left;margin-top:10px;display:inline-block;width:8px;height:8px;background-color:#5D7092"></div>' +
                element.seriesName +
                '<span style="color:#0A1933;margin-left:12px">' +
                element.data +
                "个</span></div>";
            });
            return title + result;
          },
          axisPointer: {
            // Use axis to trigger tooltip
            type: "line",
            lineStyle: {
              color: "rgba(0,29,30,0.5)",
              type: "dashed",
            },
          },
        },
        color: ["#11ADFA", "#15E0BB", "#5C7193"],
        legend: {
          right: 25,
          itemWidth: 14,
          itemHeight: 2,
          top: 0,
          textStyle: {
            //图例文字的样式
            fontSize: this.nowSize(16),
          },
          data: [
            {
              name: "外出",
              icon: "rect",
            },
            {
              name: "当前",
              icon: "rect",
            },
            {
              name: "来访",
              icon: "rect",
            },
          ],
        },
        yAxis: {
          name: "人数",
          type: "value",
          splitLine: {
            show: true,
            lineStyle: {
              type: "dashed",
              color: "#F1F1F1",
            },
          },
          // x轴下方的文字
          axisLabel: {
            show: true,
            interval: 1,
            fontSize: this.nowSize(16),
            color: "rgba(256,22,22,1)",
          },
          nameTextStyle: {
            color: "rgba(0,0,51,0.3)",
          },
        },
        series: [
          {
            name: "外出",
            data: [
              100, 240, 340, 450, 500, 435, 380, 360, 320, 100, 400, 230, 456,
              400, 100, 145, 345, 234, 340, 380, 269, 213, 400, 420, 234,
            ],
            type: "line",
            smooth: true,
            showSymbol: false,
            lineStyle: {
              fontSize: this.nowSize(16),
              color: "rgba(17,170,255,1)",
            },
            areaStyle: {
              color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
                { offset: 0, color: "rgba(17,170,255,0.2)" },
                { offset: 1, color: "rgba(17,170,255,0)" },
              ]),
            },
          },
          {
            name: "当前",
            data: [
              50, 190, 240, 350, 400, 335, 280, 260, 220, 50, 300, 130, 256,
              343, 50, 105, 245, 134, 240, 280, 169, 113, 300, 320, 134,
            ],
            type: "line",
            smooth: true,
            showSymbol: false,
            lineStyle: {
              color: "#15E0BB",
            },
            areaStyle: {
              color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
                { offset: 0, color: "rgba(21,224,187,0.2)" },
                { offset: 1, color: "rgba(21,224,187,0)" },
              ]),
            },
          },
          {
            name: "来访",
            data: [
              400, 420, 420, 470, 520, 555, 520, 580, 540, 660, 520, 470, 436,
              523, 500, 429, 445, 444, 360, 390, 329, 323, 300, 200, 200,
            ],
            type: "line",
            smooth: true,
            showSymbol: false,
            lineStyle: {
              color: "rgba(93,112,146,1)",
            },
            areaStyle: {
              color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
                { offset: 0, color: "rgba(93,112,146,0.2)" },
                { offset: 1, color: "rgba(93,112,146,0)" },
              ]),
            },
          },
        ],
      };
      this.MyChart5.setOption(option);
    },
  },
};
</script>

<style lang="scss" scoped>
.common {
  width: 100%;
  height: 27vh;
  background-color: beige !important;
}
</style>
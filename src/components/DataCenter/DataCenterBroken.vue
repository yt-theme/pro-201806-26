<template>
  <div class="broken-container">
    <div class="broken-container-upper">
      <div id="broken-pie" :style="{width:'180px',height:'180px'}"></div>
    </div>
  </div>
</template>
<script>
import echarts from 'echarts'
export default {
  name: 'DataCenterbroken',
  components: {

  },
  data() {
    return {
      charts:'',
      opinion:['工作','闲时'],
      xAxis: {
        name: '月',
        data: ['一月','二月','三月','四月','五月','六月','七月','八月','九月','十月','十一月','十二月']
      },
      yAxis: {
        name: '用量',
        type: 'value',
      }
    }
  },
  methods: {
    drawPie(id) {
      this.charts = echarts.init(document.getElementById(id))
      this.charts.setOption({
        tooltip: {
          trigger: 'item',
          formatter: '{a}<br/>{b}:{c} ({d}%)'
        },
        // legend: {
        //   orient: 'vertical',
        //   x: 'left',
        //   data:this.opinion
        // },
        series: [
          {
            name:'访问来源',
            type:'line',
            itemStyle: {
              normal: {
                color: function(params) {
                  let colorList = [
                    '#fe5461',
                    '#57b1ff'
                  ]
                  return colorList[params.dataIndex]
                }
              }
            },
            radius:['69%','80%'],
            avoidLabelOverlap: false,
            label: {
              normal: {
                show: false,
                position: 'center'
              },
              emphasis: {
                show: true,
                textStyle: {
                  fontSize: '30',
                  fontWeight: 'blod'
                }
              }
            },
            labelLine: {
              normal: {
                show: false
              }
            },
            data:this.opinionData
          }
        ]
      })
    }
  },
  mounted () {
    this.drawPie('broken-pie')
  }
}
</script>
<style scoped>
  .broken-container {
    width: 40.625%; /*520/1280*/
    height: 330px; /*330/*/
    /* box-sizing: border-box; */
    /* display: flex; */
    /* flex-wrap: wrap; */
    box-shadow: 0 0 13px #999;
    background-color: #ffffff;
    padding: 20px;
  }
  .broken-container-upper {
    display: flex;
  }
  h2 {
    font-weight: normal;
    line-height: 40px;
  }
  p {
    line-height: 40px;
  }
</style>

<template>
  <div class="pie-container">
    <h3>缴费统计</h3>
    <div class="pie-container-upper">
      <h4>缴费统计饼图: (单位: 户)</h4>
      <div id="pie-pie" :style="{width:'180px',height:'180px'}"></div>
    </div>
    <div>
      <p><i></i>{{"实缴:" + '' }}</p>
      <p><i></i>{{"应缴:" + '' }}</p>
      <p><i></i>{{"未缴:" + '' }}</p>
    </div>
  </div>
</template>
<script>
import echarts from 'echarts'
export default {
  name: 'DataCenterpieCircle',
  components: {

  },
  data() {
    return {
      charts:'',
      opinion:['实缴','未缴'],
      opinionData:[
        {value:335, name:'实缴'},
        {value:1548, name:'未缴'}
      ]
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
            name:'缴费状况',
            type:'pie',
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
            radius:['0%','80%'],
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
    this.drawPie('pie-pie')
  }
}
</script>
<style scoped>
  .pie-container {
    width: 285px; /*520/1280*/
    height: 330px; /*330/*/
    /* box-sizing: border-box; */
    /* display: flex; */
    /* flex-wrap: wrap; */
    box-shadow: 0 0 13px #999;
    background-color: #ffffff;
    padding: 20px;
  }
  .pie-container-upper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  h3 {
    font-weight: normal;
    line-height: 32px;
  }
  p {
    line-height: 40px;
  }
</style>

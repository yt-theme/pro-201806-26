<template>
  <div class="hollow-container">
    <div class="hollow-container-upper">
      <div id="hollow-pie" :style="{width:'180px',height:'180px'}"></div>
      <div>
        <h2>您的社区还不够完美哦,加油吧!</h2>
        <p><i></i>每日工作,完成率90%</p>
        <p><i></i>业主事件,完成率70%</p>
        <p><i></i>周期事务,完成率100%</p>
        <p><i></i>耗水量环比去年,-1.5%</p>
      </div>
    </div>
    <div>
      <p><i></i>耗电量环比去年,+1.7%</p>
      <p><i></i>费用欠缴状况,缴费率70%</p>
    </div>
  </div>
</template>
<script>
import echarts from 'echarts'
export default {
  name: 'DataCenterHollowCircle',
  components: {

  },
  data() {
    return {
      charts:'',
      opinion:['工作','闲时'],
      opinionData:[
        {value:335, name:'工作'},
        {value:1548, name:'闲时'}
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
            name:'访问来源',
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
    this.drawPie('hollow-pie')
  }
}
</script>
<style scoped>
  .hollow-container {
    width: 40.625%; /*520/1280*/
    height: 330px; /*330/*/
    /* box-sizing: border-box; */
    /* display: flex; */
    /* flex-wrap: wrap; */
    box-shadow: 0 0 13px #999;
    background-color: #ffffff;
    padding: 20px;
  }
  .hollow-container-upper {
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

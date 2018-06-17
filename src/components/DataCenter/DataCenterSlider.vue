<template>
<div class="slider-container">
  <div v-for="i in lineData" class="slider-single">
    <p>{{i.type}}</p>
    <el-progress :stroke-width="14" :percentage="i.process"></el-progress>
    <div class="slider-aff">
      <span>{{'工作量' + i.total}}</span>
      <span>{{'完成数量' + i.completed}}</span>
      <span>{{'参与人数' + i.population}}</span>
    </div>
  </div>
</div>
</template>

<script>
  export default {
    data() {
      return {
        lineData: [
          {
            type: '日常工作',
            process: '90',
            total: '10',
            completed: '9',
            population: '30'
          },
          {
            type: '周期事务',
            process: '100',
            total: '10',
            completed: '10',
            population: '5'
          },
          {
            type: '业主事件',
            process: '70',
            total: '10',
            completed: '7',
            population: '5'
          }
        ]
      }
    },
    methods: {
      formatTooltip(val) {
        return val / 100;
      }
    }
  }
</script>
<style scoped>
  .slider-container {
    width: 40.625%;
    height: 330px;
    box-shadow: 0 0 13px #999;
    background-color: #ffffff;
    padding: 20px;
  }
  .slider-aff {
    display: flex;
    justify-content: space-between;
  }
  .slider-single {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin-bottom: 1.5em;
  }
</style>

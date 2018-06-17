<template>
<div class="container">
  <header>
    <div class="header-nav">
      <ul>
        <li v-for="i in tabs" @click=tabChange(i.id)>{{i.name}}</li>
      </ul>
    </div>
    <div>

    </div>
  </header>
  <main>
    <div :is="toView"></div>
  </main>
</div>
</template>

<script>
import DataCenter from "../DataCenter/DataCenter.vue"
import EventManage from "../EventManage/EventManage.vue"
import Equipment from "../Equipment/Equipment.vue"
import TrafficManage from "../TrafficManage/TrafficManage.vue"
import EmployeeManage from "../EmployeeManage/EmployeeManage.vue"
import MoneyManage from "../MoneyManage/MoneyManage.vue"
import FunctionWhole from "../FunctionWhole/FunctionWhole.vue"
export default {
  name: 'HelloWorld',
  components: {
    DataCenter,
    EventManage,
    Equipment,
    TrafficManage,
    EmployeeManage,
    MoneyManage,
    FunctionWhole
  },
  data () {
    return {
      toView: 'DataCenter',
      tabs: [
        {name:"数据中心",id:1},
        {name:"事件管理",id:2},
        {name:"物联设备",id:3},
        {name:"通行管理",id:4},
        {name:"员工管理",id:5},
        {name:"财务管理",id:6},
        {name:"功能大全",id:7}
      ]
    }
  },
  methods: {
    tabChange(id) {
      switch (id) {
        case 1:
          this.toView = 'DataCenter'
          break;
        case 2:
          this.toView = 'EventManage'
        break;
        case 3:
          this.toView = 'Equipment'
        break;
        case 4:
          this.toView = 'TrafficManage'
        break;
        case 5:
          this.toView = 'EmployeeManage'
        break;
        case 6:
          this.toView = 'MoneyManage'
        break;
        case 7:
          this.toView = 'FunctionWhole'
        break;
        default:
          break;
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  display: flex;
  flex-direction: column;
}
header {
  width: 100vw;
  height: 170px;
  background-color: #56b2ff;
}
.header-nav> ul {
  display: flex;
  list-style: none;
}
.header-nav> ul> li {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 135px;
  height: 120px;
  cursor: pointer;
}
main {
  width: 100vw;
  height: 100%;
}
</style>

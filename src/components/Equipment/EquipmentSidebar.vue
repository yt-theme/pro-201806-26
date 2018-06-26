<template>
  <div class="Equipment-sidebar-container">
    <ul>
      <li><div><i></i>门禁设备</div></li>
      <li><div><i></i>道闸设备</div></li>
      <li><div><i></i>梯控</div></li>
      <li><div><i></i>小区监控</div></li>
      <li><div><i></i>水表</div></li>
      <li><div><i></i>电表</div></li>
      <li><div><i></i>楼内照明</div></li>
      <li><div><i></i>路灯</div></li>
      <li><div><i></i>环境监测</div></li>
      <li><div><i></i>环境监测</div></li>
      <li><div><i></i>报警设备</div></li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'EquipmentSidebar'
}
</script>
<style scoped>
  .Equipment-sidebar-container {
    width: 12.5vw;
    height: 81vh;
    background-color: #eaedf2;

    overflow: auto;
  }
  .Equipment-sidebar-container> ul {
    list-style: none;
  }
  .Equipment-sidebar-container> ul> li {
    display: block;
    padding: 20px 30px;
    box-sizing: border-box;
    color: #999999;
    border-bottom: 1px solid #cfd8e7;
    cursor: pointer;
  }
 </style>

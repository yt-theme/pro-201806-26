<template>
  <div class="DataCenter-container">
    <DataCenterHollowCircle></DataCenterHollowCircle>
    <DataCenterPieCircle></DataCenterPieCircle>
    <DataCenterTable></DataCenterTable>
    <DataCenterSlider></DataCenterSlider>
    <DataCenterBroken></DataCenterBroken>
  </div>
</template>
<script>
import DataCenterHollowCircle from "./DataCenterHollowCircle.vue"
import DataCenterPieCircle from './DataCenterPieCircle.vue'
import DataCenterTable from './DataCenterTable.vue'
import DataCenterSlider from './DataCenterSlider.vue'
import DataCenterBroken from './DataCenterBroken.vue'
export default {
  name: "DataCenter",
  components: {
    DataCenterHollowCircle,
    DataCenterPieCircle,
    DataCenterTable,
    DataCenterSlider,
    DataCenterBroken
  }
}
</script>
<style scoped>
  .DataCenter-container {
    display: flex;
    flex-wrap:wrap;
    width: 100vw;
    height: 100%;
  }
</style>

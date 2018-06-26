<template>
  <div class="EquipmentBody-container">
    <EquipmentMenJin></EquipmentMenJin>
  </div>
</template>
<script>
import EquipmentMenJin from './EquipmentBody_menjin.vue'
export default {
  name: 'EquipmentBody',
  components: {
    EquipmentMenJin
  }
}
</script>
<style scoped>
  .EquipmentBody-container {
    width: 87.5vw;
    height: 81vh;
    padding: 25px;
    box-sizing: border-box;
  }
</style>

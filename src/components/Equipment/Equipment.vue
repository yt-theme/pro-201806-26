<template>
  <div class="Equipment-container">
    <EquipmentSidebar></EquipmentSidebar>
    <EquipmentBody></EquipmentBody>
  </div>
</template>
<script>
import EquipmentSidebar from './EquipmentSidebar.vue'
import EquipmentBody from './EquipmentBody.vue'
export default {
  name: 'Equipment',
  components: {
    EquipmentSidebar,
    EquipmentBody
  }
}
</script>
<style scoped>
  .Equipment-container {
    display: flex;
  }
</style>
